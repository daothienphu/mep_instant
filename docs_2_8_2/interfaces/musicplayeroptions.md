[@mep.tech/instant](../DOCS.md) / [Exports](../modules.md) / MusicPlayerOptions

# Interface: MusicPlayerOptions

## Hierarchy

* [*MusicPlayerListeners*](musicplayerlisteners.md)

  ↳ **MusicPlayerOptions**

## Table of contents

### Properties

- [autoplay](musicplayeroptions.md#autoplay)
- [loop](musicplayeroptions.md#loop)
- [onEnd](musicplayeroptions.md#onend)
- [onLoad](musicplayeroptions.md#onload)
- [onPause](musicplayeroptions.md#onpause)
- [onPlay](musicplayeroptions.md#onplay)
- [onSeek](musicplayeroptions.md#onseek)
- [onStop](musicplayeroptions.md#onstop)
- [rate](musicplayeroptions.md#rate)
- [src](musicplayeroptions.md#src)

## Properties

### autoplay

• `Optional` **autoplay**: *boolean*

Set to true to automatically start playback when sound is loaded.

**`default`** `false`

Defined in: index.ts:287

___

### loop

• `Optional` **loop**: *boolean*

Set to true to automatically loop the sound forever.

**`default`** `false`

Defined in: index.ts:280

___

### onEnd

• `Optional` **onEnd**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound finishes playing (if it is looping, it'll fire at the end of each loop).

Inherited from: [MusicPlayerListeners](musicplayerlisteners.md).[onEnd](musicplayerlisteners.md#onend)

Defined in: index.ts:266

___

### onLoad

• **onLoad**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound is loaded.

Inherited from: [MusicPlayerListeners](musicplayerlisteners.md).[onLoad](musicplayerlisteners.md#onload)

Defined in: index.ts:242

___

### onPause

• `Optional` **onPause**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound has been paused.

Inherited from: [MusicPlayerListeners](musicplayerlisteners.md).[onPause](musicplayerlisteners.md#onpause)

Defined in: index.ts:256

___

### onPlay

• `Optional` **onPlay**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound begins playing.

Inherited from: [MusicPlayerListeners](musicplayerlisteners.md).[onPlay](musicplayerlisteners.md#onplay)

Defined in: index.ts:247

___

### onSeek

• `Optional` **onSeek**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound has been seeked.

Inherited from: [MusicPlayerListeners](musicplayerlisteners.md).[onSeek](musicplayerlisteners.md#onseek)

Defined in: index.ts:251

___

### onStop

• `Optional` **onStop**: [*MusicPlayerCallback*](../modules.md#musicplayercallback)

Fires when the sound has been stopped.

Inherited from: [MusicPlayerListeners](musicplayerlisteners.md).[onStop](musicplayerlisteners.md#onstop)

Defined in: index.ts:261

___

### rate

• `Optional` **rate**: *number*

The rate of playback. 0.5 to 4.0, with 1.0 being normal speed.

**`default`** `1.0`

Defined in: index.ts:294

___

### src

• **src**: *string*

The sources to the track(s) to be loaded for the sound (URLs or base64 data URIs).

Defined in: index.ts:273
