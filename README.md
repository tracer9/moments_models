# Pretrained models for Moments in Time Dataset

We release the pre-trained models trained on [Moments in Time](http://moments.csail.mit.edu/).

### Download the Models

* Clone the code from Github:
```
    git clone https://github.com/metalbubble/moments_models.git
    cd moments_models
```

### Models

* RGB model in PyTorch (ResNet50 pretrained on ImageNet). Tested sucessfully in PyTorch0.3 + python36.
```
    python test_model.py
```

* Dynamic Image model in Caffe: use the [testing script](compute_prob_dynImg.py).

* TRN models is at [this repo](https://github.com/metalbubble/TRN-pytorch). To use the TRN model trained on Moments:

Clone the TRN repo and Download the pretrained TRN model

```
git clone --recursive https://github.com/metalbubble/TRN-pytorch
cd TRN-pytorch/pretrain
./download_models.sh
cd ../sample_data
./download_sample_data.sh
```

Test the pretrained model on the sample video

![result](http://relation.csail.mit.edu/data/juggling.gif)

```
python test_video.py --arch InceptionV3 --dataset moments \
    --weight pretrain/TRN_moments_RGB_InceptionV3_TRNmultiscale_segment8_best.pth.tar \
    --frame_folder sample_data/juggling_frames 

RESULT ON sample_data/juggling_frames
1.000 -> juggling
0.000 -> catching
0.000 -> balancing

```


### Reference

Mathew Monfort, Bolei Zhou, Sarah Adel Bargal, Alex Andonian, Tom Yan, Kandan Ramakrishnan, Lisa Brown, Quanfu Fan, Dan Gutfreund, Carl Vondrick, Aude Oliva. 'Moments in Time Dataset: one million videos for event understanding'. arXiv:1801.03150. [pdf](https://arxiv.org/pdf/1801.03150.pdf), [bib](http://moments.csail.mit.edu/data/moments.bib)


### Acknowledgements

The project is supported by MIT-IBM Watson AI Lab and IBM Research.
