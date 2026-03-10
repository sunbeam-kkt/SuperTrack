# SuperTrack: Semantic Unified Pseudo-segmentation and Enhanced Representation for UAV Tracking

### This is the official code of the paper ***SUPER-Track: Semantic Unified Pseudo-segmentation and Enhanced Representation for UAV Tracking***.

*Robust UAV tracking remains challenging in cluttered scenes due to severe appearance ambiguity, frequent occlusion, and strong motion interference, especially in multi-UAV scenarios. To address these issues, we propose SuperTrack, a two-stage UAV tracking framework composed of a pseudo-segmentation-enhanced detector and a semantic-assisted trajectory association module. In the detection stage, we introduce an instance semantic pseudo-segmentation strategy to improve foreground-background separability for small UAVs, a spatio-temporal consistency regularization to preserve temporal coherence under noise and occlusion, and a background hard negative mining scheme to suppress confusing background responses. In the association stage, instead of relying solely on frame-level appearance cues, we summarize recent trajectory statistics within temporal windows and convert them into template-based textual prompts, which are encoded by a frozen text encoder into compact semantic embeddings for association refinement. This design complements geometry-based matching with a structured semantic context extracted from short-term trajectory statistics, providing a stable, structured semantic representation of trajectory cues. Extensive experiments on Track 3, Anti-UAV410, LaSOT, LaSOT$_{ext}$, GOT-10K, and TrackingNet demonstrate that SuperTrack achieves competitive performance across both UAV-specific and generic tracking benchmarks.*

The structure of the UAV detection part is shown as subfigure:

![IPS-SOD](https://github.com/sunbeam-kkt/SuperTrack/blob/main/SBD-based%20on%20YOLOv13.png)

Correspondingly, the structure of UAV target tracking is shown in the following figure:

![CSPTracker](https://github.com/sunbeam-kkt/SuperTrack/blob/main/Super-Tracker.png)

We can easily start training the SUPERTrack model by:

```python
python train.py
```

Then run the following code to train the tracker:

```python
python csptracker.py
```

Calculate the MOTA value using the detection code officially released by CVPR. First, enter folder __MultiUAV_Baseline_code_and_submissi__, then run:

```python
python tool/2_compute_MOTA.py
```

And you also can test the trained model by run:

```python
python test.py
```

The visualization of SUPERTrack on AntiUAV410 datatset is shown in the following figure:

![visualization](https://github.com/sunbeam-kkt/SUPERTrack-main/blob/main/AntiUAV410.jpg)

### Acknowledgement
Thanks for the [Dist-Tracker](https://github.com/earth-insights/Dist-Tracker) and [YOLOv13](https://github.com/iMoonLab/yolov13) library, which helps us to quickly implement our ideas.

### Citation
If our work is useful for your research, please consider citing.

