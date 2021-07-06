@mep.tech/instant / [Exports](modules.md)

# MEPInstant
Top level namespace for the Instant Games SDK.

## initializeAsync()

Initializes the SDK library. This should be called before any other SDK functions.

**Examples**

```ts

MEPInstant.initializeAsync().then(function() {
  // Many properties will be null until the initialization completes.
  // This is a good place to fetch them:
  var platform = MEPInstant.getPlatform(); // 'IOS'
  var sdkVersion = MEPInstant.getSDKVersion(); // '2.0'
  var playerID = MEPInstant.getPlayerID();
});

```

Returns [Promise\<void\>][promise] that resolves when the SDK is ready to use.

## getSDKVersion()

The string representation of this SDK version.

**Examples**

```ts

var sdkVersion = MEPInstant.getSDKVersion(); // '2.0'

```

Returns **string** The SDK version.

## getPlatform()

The platform on which the game is currently running.

**Examples**

```ts

var platform = MEPInstant.getPlatform(); // 'IOS'

```

Returns **string** The platform.

## getPlayerId()

Get the id of the player.

**Examples**

```ts

var platform = getPlayerId(); // '123'

```

Returns **string** The player id.

## startGameAsync()

Start the game initialization flow.

**Examples**

```ts

MEPInstant.startGameAsync().then(function(song: Song) {
  myGame.start(song);
});

```

Returns [Promise\<Song\>](#song) that resolves when game is loaded and data is fulfilled.

## getNotesAsync()

Read notes data from the level file.

**Parameters**

 - `levelUrl` **string** The link to level file.

**Examples**

```ts

MEPInstant.getNotesAsync().then(function(notes: Note[]) {
  myGame.createObstacles(notes);
});

```

Returns [Promise\<Note[]\>](#note) that resolves when the notes data is fetched.

## onPause()

Set a callback to be fired when a pause event is triggered.

**Parameters**

 - `func` [Function][function] A function to call when a pause event occurs.

**Examples**

```ts

MEPInstant.onPause(function() {
  console.log('Pause event was triggered!');
  pauseGameplay();
})

```

Returns **void**

## onResume()

Set a callback to be fired when a resume event is triggered.

**Parameters**

 - `func` [Function][function] A function to call when a resume event occurs.

**Examples**

```ts

MEPInstant.onResume(function() {
  console.log('Resume event was triggered!');
  resumeGameplay();
})

```

Returns **void**

## showReviveConfirmation()

Show a revise confirmation dialog to allow user to choose whether continue or end game.

**Parameters**

 - `onYesAnswer` [Function][function] A function to call when user has chosen continue.
 - `onNoAnswer` [Function][function] A function to call when user has chosen stop.

**Examples**

```ts

MEPInstant.showReviveConfirmation(
function() {
  console.log('Continue is chose!');
  continueGameplay();
}, 
function() {
  console.log('Stop is chose!');
  stopGameplay();
})

```

Returns **void**

## endGame()

Indicates that the game has finished.

**Parameters**

 - `result` [Result](#result) The playing section result.

**Examples**

```ts

MEPInstant.endGame({ score: 23, star: 3, crown: 1, loop: 2, notes: 100, revise: 0, 1.4});

```

Returns **void**

## createMusicPlayer()

Create music player to control music playback.

**Parameters**

 - `options` [MusicPlayerOptions](#musicplayeroptions) The music player options.

**Examples**

```ts

var player = createMusicPlayer({
	src: mp3Url,
	onLoad: function() {
	   loadLevel()
   }
});

```

Returns [MusicPlayer](#musicplayer) to control music playback.

## MusicPlayer

Music player that should be used to control music playback. In our game we use [MusicPlayer](#musicplayer) to play mp3.

### play()

Play music or resume previous playback.

**Examples**

```ts

player.play();

```

Returns **void**

### pause()

Pause playback and save current position.

**Examples**

```ts

player.pause();

```

Returns **void**

### resume()

Resume previous playback.

**Examples**

```ts

player.resume();

```

Returns **void**

### stop()

Stop playback and reset to start.

**Examples**

```ts

player.stop();

```

Returns **void**

### getDuration()

Get the duration.

**Examples**

```ts

var duration = player.getDuration(); // 120

```

Returns **number** the duration in second.

### setCurrentTime()

Set the current position of a sound.

**Parameters**

 - `sec` **number** The position in second.

**Examples**

```ts

player.setCurrentTime(30);

```

Returns **number** the duration in second.

### getCurrentTime()

Get the current position of a playback.

**Examples**

```ts

var currentTime = player.getCurrentTime(); // 90

```

Returns **number** the current position in second.

### setVolume()

Set the volume for sound.

**Parameters**

 - `volume` **number** Volume from 0.0 to 1.0.

**Examples**

```ts

player.setVolume(0.9);

```

Returns **void**

### getVolume()

Get the volume.

**Examples**

```ts

var volume = player.getVolume(); // 0.6

```

Returns **number** the volume.

### isPlaying()

Check if a music is currently playing or not.

**Examples**

```ts

if (!player.isPlaying()) {
	player.play()
}

```

Returns **boolean** True if playing and false if not.

### getState()

Returns the current loaded state.

**Examples**

```ts

var state = player.getState() // "loaded"

```

Returns **string** One of *"unloaded", "loading", "loaded"*.

## Song

Represents a song data for MEPInstant.startGameAsync.

Type: [Object][object]

**Properties**

 - `id` **string** Song's id. 
 - `title` **string** Song's title.
 - `artist` **string** Artist's name.
 - `duration` number Duration in second.
 - `mp3Url` **string** Link to the mp3.
 - `levelUrl` **string** Link to level.

## Note

Represents a note data for MEPInstant.getNotesAsync.

Type: [Object][object]

**Properties**

 - `name` **string** Name of note.
 - `time` **number** Time in seconds when the note is appeared.
 - `duration` **number** Duration of note in seconds.

## Result

Represents a result data for MEPInstant.endGame.

Type: [Object][object]

**Properties**

 - `score` **number** The score.
 - `star` **number** The star.
 - `crown` **number** The crown. Earn by playing endless mode.
 - `notes` **number** The number of notes have been hit.
 - `loop` **number** The loop count. Once song is over then loop += 1.
 - `revise` **number** The revise count.
 -  `percent` **number** The percentage of current song. e.g. 0.8.

## MusicPlayerOptions

Represents option to create an [MusicPlayer](#musicplayer).

Type: [Object][object]

**Properties**

 - `src` **string** The sources to the track(s) to be loaded for the sound (URLs or base64 data URIs).
 - `loop` **boolean** Set to true to automatically loop the sound forever. **default** `false`.
 - `autoplay` **boolean** Set to true to automatically start playback when sound is loaded. **default** `false`.
 - `rate` **number** The rate of playback. 0.5 to 4.0, with 1.0 being normal speed. **default** `1.0`
 - `onLoad` [Function](function) Fires when the sound is loaded.
 - `onPlay` [Function](function) Fires when the sound begins playing.
 - `onSeek` [Function](function) Fires when the sound has been seeked.
 - `onPause` [Function](function) Fires when the sound has been paused.
 - `onStop` [Function](function) Fires when the sound has been stopped.
 - `onEnd` [Function](function) Fires when the sound finishes playing (if it is looping, it'll fire at the end of each loop).

[object]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object?fbclid=IwAR0zhSTDYOgRXVg7DReh9Me6oYtNmW04ISYNl23OU7Gbt14JRocwpVhNJSs

[promise]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise?fbclid=IwAR3Q7EVmFLpWhOqEkCiXPiqBQ-gX95wW_IiJo7gkaMnvezzbu86MmWJ7Igs

[function]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function?fbclid=IwAR1QKRld8PXFx3C0TdeaoOEQX860kA-Jjf5imwrqP2KiKK97OVdQrrGRURs
