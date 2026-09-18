## Hi there 👋

Machine learning for physiological signals and sensor systems. Research Scientist, Dept. of Surgery, Stanford School of Medicine · previously Data Scientist at Vectra AI · PhD, Electrical Engineering (USF)

I build ML and signal-processing systems that turn messy real-world sensor data — ECG, EEG, video, motion, force, audio — into deployed measurement tools. Over 9+ years I've shipped production anomaly-detection models at a cybersecurity company (>1B-row pipelines in Spark), predicted atrial fibrillation from long-term ECG at >99% accuracy, and led the algorithm side of a sensor-based surgical assessment platform at Stanford that has collected data across 200+ clinical cases and raised $5M+ in funding during my time.

**Domains:** physiological signal processing · state estimation (least-squares / MMSE / Kalman-family) · deep learning for time series and video (CNN, LSTM, transformers) · streaming speech and audio · wearable sensor systems · surgical data science

### Selected work
**[SUMER-VID](https://github.com/c-perumalla/SUMER-VID)** — surgical maneuver recognition from video
Classifies the maneuvers that make up open-surgical technique — ties, cuts, suture throws — from video of simulated procedures. A slicing pipeline turns an annotation table plus raw session recordings into labeled 2-second clips; models are TimeDistributed CNN encoders (MobileNet, then ResNet) over GRU/LSTM heads, iterated across ~25 notebook revisions, with a parallel PyTorch ResNet-50 + LSTM implementation. A separate track adapts published surgical-phase models (SV-RCNet, MTRCNet-CL) to the public Cholec80 dataset.
`Python · TensorFlow/Keras · PyTorch · OpenCV · MoviePy`

**[autoprez](https://github.com/c-perumalla/autoprez)** — real-time lyric tracking for live presentation
Listens to live singing through a microphone, tracks where the singer is in the lyrics, and advances the slide without anyone touching a keyboard. Streaming ASR (Moonshine, earlier Whisper-Live) feeds a sequential word matcher that tolerates the transcriber's mishearings via prefix and bounded-Levenshtein matching, and enforces a minimum time-on-line so that words still arriving from the *previous* line don't trigger an early transition. FastAPI + WebSocket backend, React/Vite front end. Tuning is empirical, not guessed: a WER harness scores transitions against hand-labeled ground truth, and a hill-climbing optimizer searches the parameter space across a held-out set of songs.
`Python · FastAPI · WebSockets · faster-whisper / Moonshine · RapidFuzz · React`


**[colonoscopy-gesture-recognition](https://github.com/c-perumalla/colonoscopy-gesture-recognition)** — classifying endoscope maneuvers from motion data, supporting objective skill assessment. Related publication in *Diseases of the Colon & Rectum*, 2023.

### Utilities

**[convert-to-mp3s](https://github.com/c-perumalla/convert-to-mp3s)** — batch archival of a video back-catalog as audio. Walks a channel's playlists through the YouTube Data API, downloads each video, transcodes to MP3 with ffmpeg, and deletes the source to keep disk flat. Resumable — it skips anything already converted — with per-run logging and a failure set so a long batch survives individual errors.
`Python · YouTube Data API · pytube · ffmpeg`

### Publications

14 peer-reviewed papers in IEEE venues, *Annals of Surgery*, *Journal of the American College of Surgeons*, *Journal of Surgical Research* → [Google Scholar](https://scholar.google.com/citations?user=m0OcK-QAAAAJ&hl=en)

<!-- TODO: replace YOUR_SCHOLAR_ID above with your actual Scholar ID — this link is currently broken. -->

### Contact

[LinkedIn](https://www.linkedin.com/in/calvin-perumalla/) · calvinapollos@gmail.com
