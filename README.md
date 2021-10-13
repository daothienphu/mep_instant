# MEPIntant
> Amanotes's mep_instant SDK DOC

---------------------------------------------------------

# MEPIntant SDK

| Version | Changelog | Doc | Link | Cocos extension |
| ----------- | ----------- | ----------- | ----------- | ----------- | 
| 2.5.0 | <ul><li>Fix current time precision </li><li>Save game support</li></ul> | [Doc](docs_2_5_0/DOCS.md) | [UNPKG](https://unpkg.com/@mep.tech/instant@2.5.0/dist/mepinstant.umd.production.min.js) | [ZIP](https://d1wkdokb986dq4.cloudfront.net/mep-instant-sdk/cocos_extension/mep_instant_2.3.0-alpha8.zip)
| 2.5.1 | <ul><li>autoSpecificContent flag added </li> | [Doc](docs_2_5_1/DOCS.md) | [UNPKG](https://unpkg.com/@mep.tech/instant@2.5.1/dist/mepinstant.umd.production.min.js) | [ZIP](https://d1wkdokb986dq4.cloudfront.net/mep-instant-sdk/cocos_extension/mep_instant_2.3.0-alpha8.zip)
| 2.5.2 | <ul><li> specificContent flag added </li> | [Doc](docs_2_5_2/DOCS.md) | [UNPKG](https://unpkg.com/@mep.tech/instant@2.5.2/dist/mepinstant.umd.production.min.js) | [ZIP](https://d1wkdokb986dq4.cloudfront.net/mep-instant-sdk/cocos_extension/mep_instant_2.3.0-alpha8.zip)
| 2.6.0 | <ul><li> getSpecificContent function added </li> | [Doc](docs_2_6_0/DOCS.md) | [UNPKG](https://unpkg.com/@mep.tech/instant@2.6.0/dist/mepinstant.umd.production.min.js) | [ZIP](https://d1wkdokb986dq4.cloudfront.net/mep-instant-sdk/cocos_extension/mep_instant_2.6.0.zip)
 | 2.7.0 | <ul><li> Add platform hide loading screen function </li> | [Doc](docs_2_7_0/DOCS.md) | [UNPKG](https://unpkg.com/@mep.tech/instant@2.7.0/dist/mepinstant.umd.production.min.js) | [ZIP](https://d1wkdokb986dq4.cloudfront.net/mep-instant-sdk/cocos_extension/mep_instant_2.7.0.zip)

# How to enable Native-like game
- [CocosV2](misc/cocosV2.md)
- [CocosV3](misc/cocosV3.md)

## Samples
### Read and filter note

```javascript
const difficultyToOctave = {
  "SupperEasy": 4,
  "Easy": 5,
  "Medium": 6,
  "Hard": 7,
  "Expert": 9
}
function midiToNoteName(midi) {
  let notes = ["C", "C#", "D", "D#", "E", "F",
    "F#", "G", "G#", "A", "A#", "B"];
  let noteIdx = midi % 12;
  let output = {
    line: noteIdx + 1,
    noteName: notes[noteIdx],
    octave: ((midi - noteIdx) / 12) - 1
  }
  return output
}
MEPInstant.initializeAsync().then(() => {
  let binURL = 'https://music.amanotes.net/media/c01a912b-46cc-4354-9e38-ffe63d9dd503/97360c7d-979b-4c60-92d1-787cf6c6d82e.bin'
  //'https://music.amanotes.net/media/ef661fc1-395a-46c9-b87d-901add67d4ea/6dcc59f4-feb1-465f-8154-f464f90b935b.bin'
  MEPInstant.getNotesAsync(binURL)
    .then(levelData => {
      console.log(levelData)
      const notes = levelData.fullNotes;
      let notesFiltered = notes.filter(note => midiToNoteName(note.midi).octave == difficultyToOctave["Medium"])
      console.log(notesFiltered.length)
      console.log(JSON.stringify(notesFiltered))
    })
})
```
