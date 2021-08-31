[@mep.tech/instant](DOCS.md) / Exports

# @mep.tech/instant

## Table of contents

### Enumerations

- [HapticMode](enums/hapticmode.md)
- [NoteLine](enums/noteline.md)

### Interfaces

- [Configs](interfaces/configs.md)
- [GameData](interfaces/gamedata.md)
- [LevelData](interfaces/leveldata.md)
- [MusicPlayerListeners](interfaces/musicplayerlisteners.md)
- [MusicPlayerOptions](interfaces/musicplayeroptions.md)
- [Note](interfaces/note.md)
- [Result](interfaces/result.md)
- [Song](interfaces/song.md)
- [SpecificContent](interfaces/specificcontent.md)

### Type aliases

- [MusicPlayerCallback](modules.md#musicplayercallback)

### Functions

- [createCustomHapticFeedback](modules.md#createcustomhapticfeedback)
- [createHapticFeedback](modules.md#createhapticfeedback)
- [createMusicPlayer](modules.md#createmusicplayer)
- [emitCustomEvent](modules.md#emitcustomevent)
- [endGame](modules.md#endgame)
- [getBPMLine](modules.md#getbpmline)
- [getComponent](modules.md#getcomponent)
- [getDrumLine](modules.md#getdrumline)
- [getGameDataAsync](modules.md#getgamedataasync)
- [getMelodyLine](modules.md#getmelodyline)
- [getNotesAsync](modules.md#getnotesasync)
- [getPlatform](modules.md#getplatform)
- [getPlayerId](modules.md#getplayerid)
- [getSDKVersion](modules.md#getsdkversion)
- [getSoundEnergyLine](modules.md#getsoundenergyline)
- [getSpecificContent](modules.md#getspecificcontent)
- [getVocalLine](modules.md#getvocalline)
- [hidePlatformLoadingScreen](modules.md#hideplatformloadingscreen)
- [initializeAsync](modules.md#initializeasync)
- [isPvP](modules.md#ispvp)
- [loadDynamicScript](modules.md#loaddynamicscript)
- [onDisconnect](modules.md#ondisconnect)
- [onGameResult](modules.md#ongameresult)
- [onPause](modules.md#onpause)
- [onResume](modules.md#onresume)
- [onStartCountDown](modules.md#onstartcountdown)
- [onStartPvP](modules.md#onstartpvp)
- [playPredefinedHaptic](modules.md#playpredefinedhaptic)
- [readNotebotv4AsMIDI](modules.md#readnotebotv4asmidi)
- [sendGameReady](modules.md#sendgameready)
- [sendScoreRequest](modules.md#sendscorerequest)
- [setGameDataAsync](modules.md#setgamedataasync)
- [showReviveConfirmation](modules.md#showreviveconfirmation)
- [startGameAsync](modules.md#startgameasync)

## Type aliases

### MusicPlayerCallback

Ƭ **MusicPlayerCallback**: () => *void*

#### Type declaration:

▸ (): *void*

**Returns:** *void*

Defined in: index.ts:236

## Functions

### createCustomHapticFeedback

▸ **createCustomHapticFeedback**(`intensity`: *number*, `sharpness`: *number*, `duration`: *number*, `isContinuous`: *boolean*): *void*

Create haptic feedback with custom value

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`intensity` | *number* | intensity of haptic feedback   |
`sharpness` | *number* | of haptic feedback   |
`duration` | *number* | the duration of haptic feedback   |
`isContinuous` | *boolean* | of haptic feedback    |

**Returns:** *void*

Defined in: index.ts:665

___

### createHapticFeedback

▸ **createHapticFeedback**(`hapticType?`: [*HapticMode*](enums/hapticmode.md)): *void*

Create haptic feedback

**`default`** `HapticMode.mediumImpact`

#### Parameters:

Name | Type |
:------ | :------ |
`hapticType` | [*HapticMode*](enums/hapticmode.md) |

**Returns:** *void*

Defined in: index.ts:652

___

### createMusicPlayer

▸ **createMusicPlayer**(`options`: [*MusicPlayerOptions*](interfaces/musicplayeroptions.md)): MusicPlayer

Create music player to control music playback.

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`options` | [*MusicPlayerOptions*](interfaces/musicplayeroptions.md) | Music play options.   |

**Returns:** MusicPlayer

Return a music player that will be use to control music playback.

Defined in: index.ts:575

___

### emitCustomEvent

▸ **emitCustomEvent**(`eventName`: *string*, `payload`: *any*): *void*

#### Parameters:

Name | Type |
:------ | :------ |
`eventName` | *string* |
`payload` | *any* |

**Returns:** *void*

Defined in: index.ts:626

___

### endGame

▸ **endGame**(`result`: [*Result*](interfaces/result.md)): *void*

This indicates that the game has finished.

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`result` | [*Result*](interfaces/result.md) | The playing section result.    |

**Returns:** *void*

Defined in: index.ts:566

___

### getBPMLine

▸ **getBPMLine**(): *string*

Get bpm line

**Returns:** *string*

Return a note name

Defined in: index.ts:700

___

### getComponent

▸ **getComponent**(`name`: *string*): *any* \| *null*

Get MEPInstant component

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`name` | *string* | component's name. Valid values: "LevelReader": MIDI, Notebotv3 reader "LevelBotGenerator": Notebotv4 reader    |

**Returns:** *any* \| *null*

Defined in: index.ts:749

___

### getDrumLine

▸ **getDrumLine**(): *string*

Get drum line

**Returns:** *string*

Return a note name

Defined in: index.ts:716

___

### getGameDataAsync

▸ **getGameDataAsync**(): *Promise*<any\>

Gets the data associated with the individual gameplay session.

**Returns:** *Promise*<any\>

Returns a promise that resolves when data is read.

Defined in: index.ts:530

___

### getMelodyLine

▸ **getMelodyLine**(): *string*

Get melody line

**Returns:** *string*

Return a note name

Defined in: index.ts:708

___

### getNotesAsync

▸ **getNotesAsync**(`levelUrl`: *string*, `isDefaultFilter?`: *boolean*): *Promise*<[*LevelData*](interfaces/leveldata.md)\>

Read notes data from the level file.

#### Parameters:

Name | Type | Default value | Description |
:------ | :------ | :------ | :------ |
`levelUrl` | *string* | - | The link to level file.   |
`isDefaultFilter` | *boolean* | false | - |

**Returns:** *Promise*<[*LevelData*](interfaces/leveldata.md)\>

Return a promise that resolves when the note data is fetched.

Defined in: index.ts:497

___

### getPlatform

▸ **getPlatform**(): *string* \| *null*

**Returns:** *string* \| *null*

Return the platform game running on. e.g. "iOS" or "Android".

Defined in: index.ts:481

___

### getPlayerId

▸ **getPlayerId**(): *string* \| *null*

**Returns:** *string* \| *null*

Return the player's id or null.

Defined in: index.ts:488

___

### getSDKVersion

▸ **getSDKVersion**(): *string*

**Returns:** *string*

The SDK version. e.g. "2.0.0".

Defined in: index.ts:474

___

### getSoundEnergyLine

▸ **getSoundEnergyLine**(): *string*

Get sound energy line

**Returns:** *string*

Return a note name

Defined in: index.ts:724

___

### getSpecificContent

▸ **getSpecificContent**(): [*SpecificContent*](interfaces/specificcontent.md)[]

Return array of game-song specific content

**Returns:** [*SpecificContent*](interfaces/specificcontent.md)[]

Defined in: index.ts:732

___

### getVocalLine

▸ **getVocalLine**(): *string*

Get vocals line

**Returns:** *string*

Return a note name

Defined in: index.ts:692

___

### hidePlatformLoadingScreen

▸ **hidePlatformLoadingScreen**(): *void*

Hide platform's loading screen

**Returns:** *void*

Defined in: index.ts:739

___

### initializeAsync

▸ **initializeAsync**(): *Promise*<void\>

Initializes the SDK library. This should be called before any other SDK functions.

**Returns:** *Promise*<void\>

Returns a promise that resolves when the SDK is ready to use.

Defined in: index.ts:456

___

### isPvP

▸ **isPvP**(): *boolean*

Is multiplayer mode?

**Returns:** *boolean*

Defined in: index.ts:633

___

### loadDynamicScript

▸ **loadDynamicScript**(`urlSrc`: *string*, `onComplete`: Function \| *any*): *void*

Injectect script runtime

#### Parameters:

Name | Type |
:------ | :------ |
`urlSrc` | *string* |
`onComplete` | Function \| *any* |

**Returns:** *void*

Defined in: index.ts:640

___

### onDisconnect

▸ **onDisconnect**(`callback`: () => *void* \| *null*): *void*

PvP mode:

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`callback` | () => *void* \| *null* | callback will be triggered when app disconnected    |

**Returns:** *void*

Defined in: index.ts:614

___

### onGameResult

▸ **onGameResult**(`callback`: () => *void* \| *null*): *void*

PvP mode: Register callback finish match

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`callback` | () => *void* \| *null* | Callback will be triggered when the game end    |

**Returns:** *void*

Defined in: index.ts:622

___

### onPause

▸ **onPause**(`callback`: () => *void*): *void*

Set a callback to be fired when a pause event is triggered.

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`callback` | () => *void* | callback that will be triggered when a pause event is triggered.    |

**Returns:** *void*

Defined in: index.ts:538

___

### onResume

▸ **onResume**(`callback`: () => *void*): *void*

Set a callback to be fired when a resume event is triggered.

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`callback` | () => *void* | callback that will be triggered when a resume event is triggered.    |

**Returns:** *void*

Defined in: index.ts:546

___

### onStartCountDown

▸ **onStartCountDown**(`callback`: () => *void* \| *null*): *void*

PvP mode: Callback show countdown

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`callback` | () => *void* \| *null* | Callback will be triggered when app show screen count down to start gameplay    |

**Returns:** *void*

Defined in: index.ts:590

___

### onStartPvP

▸ **onStartPvP**(`callback`: () => *void* \| *null*): *void*

PvP mode: Register callback start game

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`callback` | () => *void* \| *null* | Callback will be triggered when all player was ready. Game must be start    |

**Returns:** *void*

Defined in: index.ts:606

___

### playPredefinedHaptic

▸ **playPredefinedHaptic**(`pattern`: *string*): *void*

Create haptic feedback with predefined AHAP pattern

**`see`** https://developer.apple.com/documentation/corehaptics/playing_a_custom_haptic_pattern_from_a_file?language=objc

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`pattern` | *string* | ios's AHAP pattern   |

**Returns:** *void*

Defined in: index.ts:684

___

### readNotebotv4AsMIDI

▸ **readNotebotv4AsMIDI**(`url`: *string*, `isEncrypt`: *boolean*): *Promise*<[*LevelData*](interfaces/leveldata.md)\>

Read Notebotv4 file (level4) as MIDI data (LevelData)

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`url` | *string* | level4 url. Recommend encodeURI url.   |
`isEncrypt` | *boolean* | is this encrypted file or not. Level4 is encrypted file.    |

**Returns:** *Promise*<[*LevelData*](interfaces/leveldata.md)\>

Defined in: index.ts:759

___

### sendGameReady

▸ **sendGameReady**(): *void*

PvP mode: fire event to app if game ready to play

**Returns:** *void*

Defined in: index.ts:582

___

### sendScoreRequest

▸ **sendScoreRequest**(`value`: *number*): *void*

PvP mode: fire event to app for update game score

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`value` | *number* | user score    |

**Returns:** *void*

Defined in: index.ts:598

___

### setGameDataAsync

▸ **setGameDataAsync**(`data`: *any*): *void*

Sets the data associated with the individual gameplay session.

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`data` | *any* | Data to be saved.   |

**Returns:** *void*

Returns a promise that resolves when data is saved.

Defined in: index.ts:521

___

### showReviveConfirmation

▸ **showReviveConfirmation**(`onYesAnswer`: () => *void*, `onNoAnswer`: () => *void*): *void*

Show a revise confirmation dialog.

#### Parameters:

Name | Type | Description |
:------ | :------ | :------ |
`onYesAnswer` | () => *void* | Callback will be triggered when answer is 'YES'   |
`onNoAnswer` | () => *void* | Callback will be triggered when answer is 'NO'    |

**Returns:** *void*

Defined in: index.ts:555

___

### startGameAsync

▸ **startGameAsync**(): *Promise*<[*GameData*](interfaces/gamedata.md)\>

Start the game initialization flow.

**Returns:** *Promise*<[*GameData*](interfaces/gamedata.md)\>

{Promise<{
song: Object,
gameMode: Object,
player: Object
}>} Returns a promise that resolves when game is loaded and data is fulfilled.

Defined in: index.ts:512
