### GSoC EVALUATION - 1 ###

Expected Work 
1. Speech Capturing Block
2. Speech Enhancement Block
3. Features Extraction 

Completed Work
1. Speech Capturing Block
2. Speech Enhancement Block
3. Transcriber which convert speech to text using APIs
4. Features Extraction 
5. Acoustic Model

File Name - speech_capturing.py

1. It consists of speech capturing block .
2. This code is use to create dataset of live speeches.
3. "demo.wav" is a example wav file of live speech .
4. Run python speech_capturing.py . And utter some sentence for 5-10 sec. This will record wav file. 

File Name - speech_denoising.py

1. It consists of speech enhancement block.
2. This code is use to enhanced and denoised the live speeches.
3. "file.wav" is a output of enhanced version of "demo.wav".
4. For denoising I am adding Gaussian Noise to wav file then applying Butterworth lowpass filter .
5. Load wav file which we want to enhance manually by changing in the code. Then run python speech_denoising.py . It will generate enhanced wave file .

File Name - transcriber.py

1. Here transcriber consists of two parts: a producer that captures voice from microphone, and a consumer that converts this speech stream to text. These two execute in parallel. The audio recorder keeps producing chunks of the speech stream. The speech recognizer listens to this stream, consumes these chunks upon arrival and updates the transcribed text.
2. This transcriber is built by using deepspeech library or deepspeech API .
3. This transcriber is useful to compare our live speech rcongition with transcriber.
4. There is also one README for run transcriber.

Data 

1. Currently I am using VoxForge Dataset for building ASR models. Since it is small datasets. So If htere ia any error in building models I can rectify it fast. After I will use LibriSpeech , TED-LIUM datasets.
2. Crrently I have downloaded data manually but my plan is to automate data download using web-scraping.

File Name - generate_text.py

1. This code is used to extract the transcripts of the VoxForge dataset in the folder.
2. Run python generate_text.py . It will generate the transcritps of Audio file.

File Name - generate_features_and_training_data.py

1. In this code we are extracting speech recognition features like MFCC and spectrogram .
2. Then we are building Acoustic Model for training data . They are assembled into a batched format with the target character level annotations for subsequent training.
3. Run python2 generate_features_and_training_data.py .

Future Works 
1. Complete ASR end-to-end model for LibriSpeech and TEDLIUM.
2. Start making components for competed part. 


