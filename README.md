# GHOST-2.0

## TODO
- [ ] Blender code
- [ ] Blender checkpoint
- [ ] Complete instruction (project page)
- [ ] Add blender to inference script ```inference.py```
- [ ] Add segmentation model to preprocessing script ```preprocess_image.py```

```
conda create -n ghost python=3.10
pip install facenet_pytorch

conda config --add channels conda-forge
conda config --set channel_priority strict
pip install -U 'git+https://github.com/facebookresearch/fvcore'
conda install pytorch3d -c pytorch3d-nightly

pip install -r requirements.txt
python -m pip uninstall numpy
python -m pip install numpy==1.23.1
```
Install the following repositories into the ```repo``` folder:
DECA
EMOCA

## Inference
For inference run
```
python inference.py --source ./examples/images/hab.jpg --target ./examples/images/elon.jpg --save_path result.png
```

## Training
1. Download VoxCeleb2. We expect the following structure of data directory and assume images are stored in BGR format:
```
- train
    - person_id
        - video_folder
            -h5 video files
-test
```
2. Preprocess data according to the example in file ```preprocess_image.py```
3. To train Aligner, run ```python train_aligner.py```

## Citation

## Acknowledgements
This work utilizes code from the follwing repositories:
[Neural Head Reenactment with Latent Pose Descriptors](https://github.com/shrubb/latent-pose-reenactment)
[EMOPortraits: Emotion-enhanced Multimodal One-shot Head Avatars](https://github.com/neeek2303/EMOPortraits)