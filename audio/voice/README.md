# Voice lines

The main character speaks aloud once in the game: **"I wish..."** at the gate of The Island, just before the whole scene cuts to black. Nobody has recorded it yet, so the game uses a stand-in.

## To drop in a real recording

1. Record just the words **"I wish..."**, trailing off. The scene cuts to black the moment the file ends, so trim the silence at the end.
2. Name the file **`i-wish`** and give it one of these endings: `.ogg`, `.mp3`, `.m4a` or `.wav`.
3. Put it in this folder (`public/audio/voice/`), then run `npm run deploy`.

That is all. The game looks for `i-wish.ogg`, then `i-wish.mp3`, `i-wish.m4a`, `i-wish.wav`, and plays the first one it finds.

If the recording is longer than "I wish..." and you want the cut earlier, set `WISH_CUT_AFTER_SECONDS` in `src/audio/voice.ts` to the number of seconds in.

## What plays if there is no recording

1. **`i-wish.PLACEHOLDER.wav`** (this folder): text-to-speech saying "I wish". It is a stand-in, not the real voice. It is safe to delete once a recording exists.
2. If that file cannot be loaded, the browser's own speech says it.
3. If nothing can be played (muted, or no sound), the screen still cuts to black after a short pause.
