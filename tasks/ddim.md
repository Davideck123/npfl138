### Assignment: ddim
#### Date: Deadline: Jun 28, 22:00
#### Points: 3 points
#### Tests: ddim_tests
#### Examples: ddim_examples

Implement a Denoising Diffusion Implicit Model (DDIM) to unconditionally
generate images with $64×64$ resolution.

The unlabeled image data can be loaded using the
[image64_dataset.py](https://github.com/ufal/npfl138/tree/master/labs/13/image64_dataset.py)
module, with the following datasets being available:
- `oxford_flowers102`: 8k [images of flowers](https://ufal.mff.cuni.cz/~straka/courses/npfl138/2324/demos/oxford_flowers102.jpg), 67MB,
- `lsun_bedrooms`: 15k [images of bedrooms](https://ufal.mff.cuni.cz/~straka/courses/npfl138/2324/demos/lsun_bedrooms.jpg), 109MB,
- `ffhq`: 70k [images of Flickr faces](https://ufal.mff.cuni.cz/~straka/courses/npfl138/2324/demos/ffhq.jpg), 529MB.

Start with the [ddim.py](https://github.com/ufal/npfl138/tree/master/labs/13/ddim.py)
template, which contains extensive comments indicating how the architecture
should like and how the training and sampling should be performed. Note that the
template generate images to TensorBoard (after the whole training and optionally
also each `--plot_each` epoch), and the images generated by the reference
solution can be also seen in the Examples.

#### Tests Start: ddim_tests
_Note that your results may be slightly different, depending on your CPU type and whether you use a GPU._

1. `python3 ddim.py --epochs=1 --epoch_batches=16 --batch_size=8 --stages=2 --stage_blocks=2 --channels=8 --ema=0.9 --sampling_steps=8`
```
loss: 0.7859 - sample_mean: 128.2541 - sample_std: 125.8459
```

2. `python3 ddim.py --epochs=1 --epoch_batches=10 --batch_size=12 --stages=3 --stage_blocks=1 --channels=12 --ema=0.8 --sampling_steps=7`
```
loss: 0.7855 - sample_mean: 125.5367 - sample_std: 125.8327
```
#### Tests End:
#### Examples Start: ddim_examples
_Note that your results may be slightly different, depending on your CPU type and whether you use a GPU._
- `python3 ddim.py --dataset=oxford_flowers102 --epochs=70 --plot_each=10`
![oxford_flowers102 samples](https://ufal.mff.cuni.cz/~straka/courses/npfl138/2324/demos/ddim-oxford_flowers102.webp)
- `python3 ddim.py --dataset=lsun_bedrooms --epochs=100 --plot_each=10`
![lsun_bedrooms samples](https://ufal.mff.cuni.cz/~straka/courses/npfl138/2324/demos/ddim-lsun_bedrooms.webp)
- `python3 ddim.py --dataset=ffhq --epochs=100 --plot_each=10`
![ffhq samples](https://ufal.mff.cuni.cz/~straka/courses/npfl138/2324/demos/ddim-ffhq.webp)
#### Examples End:
