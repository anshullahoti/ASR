# Create virtual environment named ds06
$ python3 -m venv ./some/pyenv/dir/path/ds06

# Switch to virtual environment
$ source ./some/pyenv/dir/path/ds06/bin/activate

# Install DeepSpeech
$ pip3 install deepspeech==0.6.0

# Download and unzip en-US models, this will take a while
$ mkdir -p ./some/workspace/path/ds06
$ cd ./some/workspace/path/ds06
$ curl -LO https://github.com/mozilla/DeepSpeech/releases/download/v0.6.0/deepspeech-0.6.0-models.tar.gz
$ tar -xvzf deepspeech-0.6.0-models.tar.gz
x deepspeech-0.6.0-models/
x deepspeech-0.6.0-models/lm.binary
x deepspeech-0.6.0-models/output_graph.pbmm
x deepspeech-0.6.0-models/output_graph.pb
x deepspeech-0.6.0-models/trie
x deepspeech-0.6.0-models/output_graph.tflite

$ ls -l ./deepspeech-0.6.0-models/

# Download and unzip some audio samples to test setup
$ curl -LO https://github.com/mozilla/DeepSpeech/releases/download/v0.6.0/audio-0.6.0.tar.gz
$ tar -xvzf audio-0.6.0.tar.gz
x audio/
x audio/2830-3980-0043.wav
x audio/Attribution.txt
x audio/4507-16021-0012.wav
x audio/8455-210777-0068.wav
x audio/License.txt

$ ls -l ./audio/

# Test deepspeech
$ deepspeech --model deepspeech-0.6.0-models/output_graph.pb --lm deepspeech-0.6.0-models/lm.binary --trie ./deepspeech-0.6.0-models/trie --audio ./audio/2830-3980-0043.wav

$ deepspeech --model deepspeech-0.6.0-models/output_graph.pb --lm deepspeech-0.6.0-models/lm.binary --trie ./deepspeech-0.6.0-models/trie --audio ./audio/4507-16021-0012.wav

$ deepspeech --model deepspeech-0.6.0-models/output_graph.pb --lm deepspeech-0.6.0-models/lm.binary --trie ./deepspeech-0.6.0-models/trie --audio ./audio/8455-210777-0068.wav