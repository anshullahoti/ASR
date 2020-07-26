### ASR using DeepSpeech ###

Completed Work
1. Speech Capturing Block
2. Speech Enhancement Block
3. Transcriber which convert speech to text using APIs
4. Features Extraction 
5. Acoustic Model
6. Language Model
7. CTC Decoder
8. Data Download Script


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
5. Load wav file which we want to enhance manually by changing in the code. Then run python speech_denoising.py . It will generate enhaned wace file .

File Name - transcriber.py

1. Here transcriber consists of two parts: a producer that captures voice from microphone, and a consumer that converts this speech stream to text. These two execute in parallel. The audio recorder keeps producing chunks of the speech stream. The speech recognizer listens to this stream, consumes these chunks upon arrival and updates the transcribed text.
2. This transcriber is built by using deepspeech library or deepspeech API .
3. This transcriber is useful to compare our live speech rcongition with transcriber.
4. There is also one README for run transcriber.

Data 

1. Currently In this demo I am using VoxForge Dataset for building ASR models. Since it is small datasets. So If there is any error in building models I can rectify it fast. 

File Name - download_data.py

1. This script is for downloading data automaticlly. I am using web scraping to download the data.
2. Run python2 download_data.py you will get the data. But you have to make minor changes in script like - first you have to mention in which folder you want the data and second link of the dataset which you want to download.

File Name - generate_text.py

1. This code is used to extract the transcripts of the VoxForge dataset in the folder.
2. Run python generate_text.py . It will generate the transcritps of Audio file.

File Name - generate_features_and_training_data.py

1. In this code we are extracting speech recognition features like MFCC and spectrogram .
2. Then we are building Acoustic Model for training data . They are assembled into a batched format with the target character level annotations for subsequent training.
3. Run python2 generate_features_and_training_data.py .

File Name -train_ctc.py

1. In this code first we take inputs from acoustic model which provides us output charecter probabilites and then we query language model for evaluating the transcription.
2. In language model it will correct our grammatical errors , spelling  mistakes .
3. The file "train_ctc.py" uses a Single layer bidirectional LSTM network to predict the transcriptions from the audio features. Every 10 epochs, an example batch is decoded and printed for comparision with the target.
4. Run python2 train_ctc.py . It will print both original and decoded output. 
5. For Demo we can use our previous set up for small dataset. For 7 min. dataset it will taking around 2 hour time for train and test the model . 

Results

1. It is providing around 73% accuracy . For increasing the accuracy I am looking to increase the level in decoding model.

Remaining Work
1. Train Data for live speeches and test it for live speeches.
2. Creating Components for each part of ASR.
3. Design a UI like thing for end to end system like - You have to click start button and you have to speak then it will automatically generate transcript. 


