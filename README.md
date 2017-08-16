# SiamFC - TensorFlow
TensorFlow port of the tracking method described in the paper [*Fully-Convolutional Siamese nets for object tracking*](https://www.robots.ox.ac.uk/~luca/siamese-fc.html).

In particular, it is the improved version presented as baseline in [*End-to-end representation learning for Correlation Filter based tracking*](https://www.robots.ox.ac.uk/~luca/cfnet.html), which achieves state-of-the-art performance at high framerate. The other methods presented in the paper (similar performance, shallower network) haven't been ported yet.

**Note1**: results should be similar (i.e. slightly better or worse) than our MatConvNet implementation. However, for direct comparison please refer to the precomputed results available in the project pages or to the original code, which you can find pinned in [my GitHub](https://github.com/bertinetto).

**Note2**: at the moment this code only allows to use a pretrained net in forward mode.

## Settings things up
1) Clone the repository
`git clone https://github.com/torrvision/siamfc-tf.git`
2) `cd siamfc-tf`
3) Install the required packages
`sudo pip install -r requirements.txt`
4) `mkdir pretrained data`
5) Download the [pretrained networks](https://bit.ly/cfnet_networks) in `pretrained` and unzip the archive (we will only use `baseline-conv5_e55.mat`)
6) Download [video sequences](https://drive.google.com/file/d/0B7Awq_aAemXQSnhBVW5LNmNvUU0/view) in `data` and unzip the archive.


## Running the tracker
1) Set `video` from `parameters.evaluation` to `"all"` or to a specific sequence (e.g. `"vot2016_ball1"`)
2) See if you are happy with the default parameters in `parameters/hyperparameters.json`
3) Optionally enable visualization in `parameters/run.json`
4) Call the main script (within an active virtualenv session)
`python run_tracker_evaluation.py`

## Authors

* [**Luca Bertinetto**](https://www.robots.ox.ac.uk/~luca)
* [**Jack Valmadre**](http://jack.valmadre.net)

## References
If you find our work useful, please consider citing

↓ [Original method] ↓
```
@inproceedings{bertinetto2016fully,
  title={Fully-Convolutional Siamese Networks for Object Tracking},
  author={Bertinetto, Luca and Valmadre, Jack and Henriques, Jo{\~a}o F and Vedaldi, Andrea and Torr, Philip H S},
  booktitle={ECCV 2016 Workshops},
  pages={850--865},
  year={2016}
}
```
↓ [Improved method and evaluation] ↓
```
@article{valmadre2017end,
  title={End-to-end representation learning for Correlation Filter based tracking},
  author={Valmadre, Jack and Bertinetto, Luca and Henriques, Jo{\~a}o F and Vedaldi, Andrea and Torr, Philip HS},
  journal={arXiv preprint arXiv:1704.06036},
  year={2017}
}
```

## License
This code can be freely used for personal, academic, or educational purposes.
Please contact us for commercial use.

-------------------------------------------------------------------------------------------
# Monaj:

## Tasks
- [x] Testing the tracker on validation data. (It is working, but I did not check on a specific benchmark)
- [ ] Turning the tracker into an object segmenter, by applying a simple Grab-cut on the tracked boxes.
- [ ] Applying the video object segmenter to DAVIS dataset to get a baseline result.



