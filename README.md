# tessdata_tamil

## tamPLUS

Ongoing PLUS training with `tessdata_best/script/Tamil.traineddata` as base. (2019-11-04)

### Training Text

A small 4579 lines, 773 KB 
[training text](https://github.com/Shreeshrii/tessdata_tamil/blob/master/tamPLUS/tam.all.training_text) 
was used for generating synthetic images using the following fonts.

### Fonts used for training.

```
Arial Unicode MS
Arima Madurai
FreeSerif
Karla Tamil Inclined Italic
Karla Tamil Upright
Lohit Tamil
Lohit Tamil Classical
Nirmala UI
Noto Sans Tamil
TAMu_Kadambri
TAMu_Kalyani
TAMu_Maduram
TSCu_Comic
TSCu_Paranar
TSCu_Times
e-Grantamil
```

### New unichars added to script/Tamil.lstm-unicharset

```
ஶ 1 65,65,192,192,222,222,23,23,269,269 Tamil 174 0 174 ஶ	# ஶ [bb6 ]x
ௌ 0 0,64,235,255,366,752,0,23,149,452 Tamil 175 0 175 ௌ	# ௌ [bcc ]
ஔ 1 0,15,192,205,208,435,0,23,149,452 Tamil 176 0 176 ஔ	# ஔ [b94 ]x
• 16 64,135,156,232,40,248,0,125,66,298 Common 177 10 177 •	# • [2022 ]p
ௐ 1 0,0,199,199,202,202,5,5,261,261 Tamil 178 0 178 ௐ	# ௐ [bd0 ]x
꞉ 0 0,255,0,255,0,0,0,0,0,0 Common 179 0 179 ꞉	# ꞉ [a789 ]
ʼ 1 162,208,229,255,6,64,0,70,55,257 Common 180 0 180 ʼ	# ʼ [2bc ]x
… 16 60,143,79,232,101,332,0,45,107,337 Common 181 10 181 ...	# … [2026 ]p
```

### Finetuned traineddata files

Finetuned traineddata files from the training are provided in two directories 
[tessdata_best](https://github.com/Shreeshrii/tessdata_tamil/tree/master/tamPLUS/tessdata_best)
and [tessdata_fast](https://github.com/Shreeshrii/tessdata_tamil/tree/master/tamPLUS/tessdata_fast)
with a best (double based) and fast (int based) model for recent training checkpoints.
The best training is not always the one with the lowest CER. So, it is recommended to test
multiple traineddata files with low CER. Tesseract can improve the OCR results by 
using not only the last but the last two or three models 
(tesseract ... -l NAME1.traineddata+NAME2.traineddata+NAME3.traineddata).

### Training Status on 2019-11-4

```
OMP_THREAD_LIMIT=1    lstmeval  \
	  --model  /home/ubuntu/tesstrain/data/tam/tessdata_best/tamPlus0.107_33435.traineddata \
	  --eval_listfile data/tam/list.eval \
	  --verbosity 1

At iteration 0, stage 0, Eval Char error rate=0.23587359, Word error rate=0.82466164
```

```
OMP_THREAD_LIMIT=1    lstmeval  \
	  --model  /home/ubuntu/tesstrain/data/tam/tessdata_best/tamPlus0.124_31627.traineddata \
	  --eval_listfile data/tam/list.eval \
	  --verbosity 1

At iteration 0, stage 0, Eval Char error rate=0.27522652, Word error rate=0.77584514
```
