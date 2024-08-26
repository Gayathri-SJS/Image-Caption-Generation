# Image Caption Generation using Attention Mechanisms

This project extends the implementation of the original Show, Attend and Tell model by experimenting with various attention mechanisms and decoder architectures to compare BLEU scores.

## Architectural Variants Implemented:

- Bahdanau Attention (Base Model)
- Luong’s Attention
- Adaptive Attention
- GRU-based Decoder
- Teacher Forcing

## Prerequisites

- Python 3.6 or higher
- Install the required Python packages by running:

```bash
pip install -r requirements.txt
```

## Dataset

The dataset used is the COCO dataset. Download the training and validation images and organize them in the following directories:

```bash
data/coco/imgs/train2014/
data/coco/imgs/val2014/
```

Download the COCO dataset split JSON file (from Deep Visual-Semantic Alignments) and place it in:

```bash
data/coco/
```
The file should be named dataset.json.

## Preprocessing

Before training, you need to preprocess the dataset to generate the necessary JSON files. Run:

```bash
python generate_json_data.py
```

## Training

### Bahdanau Attention (Base Model)

To train the model using Bahdanau Attention (the base model), follow these steps:

1. Rename BahdanauAttention.py to Attention.py:

```bash
mv BahdanauAttention.py Attention.py
```

2. Start training by running:

```bash
python train.py
```

The models will be saved in the model/ directory, and training statistics will be saved in runs/.

### Luong’s Attention

To train the model using Luong’s Attention, follow these steps:

1. Rename LuongsAttention.py to Attention.py:

```bash
mv LuongsAttention.py Attention.py
```

2. Rename decoderLuongs.py to decoder.py:

```bash
mv decoderLuongs.py decoder.py
```

3. Start training by running:

```bash
python train.py
```

### Adaptive Attention

To train the model using Adaptive Attention, follow these steps:

1. Rename AdaptiveAttention.py to Attention.py:

```bash
mv AdaptiveAttention.py Attention.py
```

2. Start training by running:

```bash
python train.py
```

### GRU-Based Decoder

To train the model using a GRU-based decoder, ensure the GRU implementation is included in the decoder.py file (already set up in the provided files). Then, start training:


```bash
python train.py
```

### Teacher Forcing

Teacher Forcing is implemented as part of the training procedure. To use Teacher Forcing, set the appropriate flag or parameter within train.py.


## Monitoring Training

You can monitor the training process using TensorBoard. 
Run:

```bash
tensorboard --logdir runs
```

## Generating Captions

To generate captions using the trained model:

```bash
python generate_caption.py --img-path <PATH_TO_IMG> --model <PATH_TO_MODEL>
```

Replace <PATH_TO_IMG> with the path to the image file and <PATH_TO_MODEL> with the path to the trained model file.

## BLEU scores comparison

<img width="400" alt="image" src="https://github.com/user-attachments/assets/630c16d8-1dca-4302-8c49-eaeb860ce3b8"> <img width="400" alt="image" src="https://github.com/user-attachments/assets/c9c60d04-e4dc-47a7-a3a8-bc1eb25bc034">

<img width="400" alt="image" src="https://github.com/user-attachments/assets/53d23d9b-e4f5-4134-8536-b2034cb0eafb"> <img width="400" alt="image" src="https://github.com/user-attachments/assets/b012853b-16ab-4e40-bb53-a8c8b951bf23">

<img width="555" alt="image" src="https://github.com/user-attachments/assets/83c1aae2-5df4-4aec-9c69-4cb7b8f6bdf1">



## Conclusion

This project extends the Show, Attend and Tell implementation by comparing different attention mechanisms and decoder architectures. Rename the appropriate files and follow the commands to execute different implementations.

## Reference

[Show, Attend and Tell](https://arxiv.org/pdf/1502.03044.pdf)
