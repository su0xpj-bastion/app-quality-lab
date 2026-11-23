# app-quality-lab

Quality engineering for apps people touch: a photo and video editor on iPhone, iPad and Mac, the video-editing engine underneath it, on-device AI features, live AI video, and a streaming AI-answer web app. The tests check what a user would notice: the right frame, the right colour, a button a screen reader can reach, a lag you can feel.

Seven projects, each in its own folder with its own README, scripts and GitHub Actions workflow. A workflow runs only when its folder changes. The Apple projects run on macOS runners with Xcode; their UI tests run on iPhone and iPad simulators, not physical devices.

| Project | What it is, in plain terms | Proof |
|---|---|---|
| [proof-sheet](proof-sheet/) | A photo and video editor for iPhone, iPad and Mac with a test for all 45 things a user does in it, from import to client approval. Robots tap through the app on iPhone and iPad simulators, including right-to-left Arabic, large text and split windows | 13 planted bugs, each caught; found real bugs including buttons screen-reader users couldn't reach and photos exporting about 25% too dark |
| [enact-probe](enact-probe/) | An iPhone app and test kit that measures how responsive a live AI-generated video feels: touch-to-screen delay, freezes, interruptions, sound out of sync | 11 checks, 8 planted bugs, each caught |
| [frame-exact](frame-exact/) | The timing engine behind a video editor, tested to the exact frame: timecode, cuts, speed changes, audio sync, edit-list export | 8 planted bugs, each caught |
| [barcode-frames](barcode-frames/) | Video editing tests where every frame carries a barcode, so real cuts and speed changes can be read back frame by frame | 6 planted bugs, each caught |
| [timeline-ml](timeline-ml/) | Tests for cuts that snap to the beat and for jumping to a spoken word, graded on tracks with known answers | 8 planted bugs, each caught |
| [vision-gate](vision-gate/) | Report cards for on-device AI photo features (straighten, smart crop, tracking, text recognition, duplicates) on images with known answers | 9 planted bugs, each caught |
| [web-e2e-qa](web-e2e-qa/) | A streaming AI-answer web app tested in Chrome, Firefox and Safari at phone, tablet and desktop sizes, including accessibility and visual checks | 166 tests; found 2 real Firefox bugs |
