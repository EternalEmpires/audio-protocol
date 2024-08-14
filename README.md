# Audio Protocol

We use websockets to enable audio playback. below you will find information on what the websocket messages sent from our server look like. Our servers do not accept messages. They only send them.

Audio Server URL: `ws://audioserver.eternalempires.net/?secret={YOUR_SECRET_HERE}`

<hr>

## When an audio starts

### Schema:
| Field | Value | Required |
|---|---|---|
| type | The type of the action. 'start' | true |
| audio | The URL of the audio to start | true |
| startTime | The start time in seconds e.g. 2 | false |

### Example:
```json
{
  "type": "start",
  "audio": "https://cdn.eternalempires.net/audio/es/6b442703-488b-4a63-9102-9d7b86d0dd1c.mp3",
  "startTime": 2
}
```

<hr>

## When an audio stops
### Schema:
| Field | Value | Required |
|---|---|---|
| type | The type of the action. 'stop' | true |
| audio | The URL of the audio to stop | true |

### Example:
```json
{
  "type": "stop",
  "audio": "https://cdn.eternalempires.net/audio/es/6b442703-488b-4a63-9102-9d7b86d0dd1c.mp3",
}
```

<hr>

## When an audio updates its volume
### Schema:
| Field | Value | Required |
|---|---|---|
| type | The type of the action. 'update-volume' | true |
| audio | The URL of the audio to update the volume of | true |
| volume | The volume to set the audio to (From 0 to 100) | true |

### Example:
```json
{
  "type": "update-volume",
  "audio": "https://cdn.eternalempires.net/audio/es/6b442703-488b-4a63-9102-9d7b86d0dd1c.mp3",
  "volume": 70
}
```
