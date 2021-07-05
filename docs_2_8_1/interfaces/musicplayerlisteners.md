[@mep.tech/instant](../DOCS.md) / [Exports](../modules.md) / MusicPlayerListeners

# Interface: MusicPlayerListeners

## Hierarchy

* **MusicPlayerListeners**

  ↳ [*MusicPlayerOptions*](musicplayeroptions.md)

## Table of contents

### Properties

- [onEnd](musicplayerlisteners.md#onend)
- [onLoad](musicplayerlisteners.md#onload)
- [onPause](musicplayerlisteners.md#onpause)
- [onPlay](musicplayerlisteners.md#onplay)
- [onSeek](musicplayerlisteners.md#onseek)
- [onStop](musicplayerlisteners.md#onstop)

## Properties

### onEnd

• `Optional` **onEnd**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound finishes playing (if it is looping, it'll fire at the end of each loop).

Defined in: index.ts:266

___

### onLoad

• **onLoad**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound is loaded.

Defined in: index.ts:242

___

### onPause

• `Optional` **onPause**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound has been paused.

Defined in: index.ts:256

___

### onPlay

• `Optional` **onPlay**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound begins playing.

Defined in: index.ts:247

___

### onSeek

• `Optional` **onSeek**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound has been seeked.

Defined in: index.ts:251

___

### onStop

• `Optional` **onStop**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound has been stopped.

Defined in: index.ts:261
