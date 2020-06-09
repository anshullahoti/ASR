######## SPEECH CAPTURING #######

Filename - speech_capturing.py

1. It will reccord live speech.
2. We will use it as to create our own datasets .

Future Work For Live Speeches
1. We will use live speeches with already trained model and figure out how we increase our accuracy for these cases. Like live speeches are not present in training data.
2. So we have to figure out that if new data comes which is not present in training set then what we will do.


##### SPEECH DENOISING ######
Filename - speech_denoising.py

1. It is very important step because it may affect our ASR accuracy by huge amount.
2. In this file we are doing two things:-
    1. Reduced Noise (High SNR)
    2. Trim Silences
3. We are using various methods for reducing noise :-
    1. Using Power
    2. Using Centroid Analysis
    3. Using MFCC Features
    4. Using Median 

Future work for speech enhancement/denoising

1. We can use many filter banks algorithm and see the results by calculating SNR values and then determine which method is more useful.