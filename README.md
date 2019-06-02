### Ubottu
This repository contains the source code for the models used in the following paper:

The Ubuntu Dialogue Corpus: A Large Dataset for Research in Unstructured Multi-Turn Dialogue Systems [arXiv:1506.08909](http://arxiv.org/abs/1506.08909). 

#### Dependencies
* Python 2.7
* Theano bleeding-edge
* Lasagne
* Pyprind

#### Usage
Fetch the pickled data:
```
cd src
wget http://dataset.cs.mcgill.ca/ubuntu-corpus-1.0/ubuntu_blobs.tgz
tar zxvf blobs.tgz
```

To reproduce the results in the original paper, use the following incantations.

RNN:
```
python main.py --encoder rnn --batch_size=512 --hidden_size=50 --optimizer adam --lr 0.001 --fine_tune_W=True --fine_tune_M=True --input_dir dataset_1MM
```

LSTM:
```
python main.py --encoder lstm --batch_size=256 --hidden_size=300 --optimizer adam --lr 0.001 --fine_tune_W=True --fine_tune_M=True --input_dir dataset_1MM
```

TFIDF:
```
python tfidf.py
```
