# pinyin-quiz-audio

Audio clips for the 拼音小测 (pinyin quiz) in the `primary-school-language-teacher` skill: one clip per 例句 in its question bank, ready to send in WhatsApp.

**This is not MOE syllabus.** The sentences are classroom practice written for the quiz, and the voice is machine-generated.

## Layout

- `<词语>-<n>.mp3` — the word's n-th 例句 (1-3, in the bank's order), spoken. MP3, mono, 24 kHz: the file to send in WhatsApp as an audio message.
- `manifest.json` — `词语 → [{例句, mp3}]`, each 例句 exactly as the bank writes it, 【**…**】 marks included. Find the clip for a question by matching its sentence.
- `review.md` — the clips whose word has a 多音字 that the quiz uses as a distractor. The voice reads characters, not 拼音, so check these by ear.

## Using it

Send a clip **with the reveal**, after the child has answered: it says the word aloud, so before the answer it gives the answer away.

A local clone is read directly. Without one, fetch over HTTPS, URL-encoding the file name:

```
https://raw.githubusercontent.com/shadowandy/pinyin-quiz-audio/main/manifest.json
https://raw.githubusercontent.com/shadowandy/pinyin-quiz-audio/main/%E8%A6%81%E6%B1%82-1.mp3
```

## Regenerating

Everything here except this README is generated. In the skill's source repo this folder is a clone of this one; regenerate there with `tools/generate_quiz_audio.py` (`--word <词语> --force` to remake one word), then commit and push.
