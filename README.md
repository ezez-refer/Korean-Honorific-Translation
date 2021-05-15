# Korean Honorific Neural Machine Translation

## Getting Started

### Step 1. Preprocess the data
```
!python preprocess.py
```
The source text file(`src`) and target text file(`tgt`)  
default tokenize : `Mecab`+`SentencePiece`.

### Step 2. Train the model
```
!python train.py
```
If you want to continue training the model, add `--train_from (model path)/model.pt` later.

### Step 3. Translate
```
!python translate.py -model data/model/model.pt -src data/src-test.txt -tgt data/tgt-test.txt -replace_unk -verbose -gpu 0
```

### Step 4. Postprocess
```
!python ./onmt/tools/spacing.py -i ./data/pred.txt -o ./data/pred_sp.txt```

### Step 5. Scoring the model
```
!perl tools/multi-bleu.perl data/tgt-test.txt < data/pred.txt
```

## Reference
https://github.com/OpenNMT/OpenNMT-py
