# CardioceptionVR

## Overview

This repository contains the source code for IEEE TVCG (ISMAR 2023) paper "Is that my Heartbeat? Measuring and Understanding Modality-dependent Cardiac Interoception in Virtual Reality".

Code clean up is still under way. None of the `Assets` are included in this repo to save space. If you want to replicate this study, please reach out to Rayna Ney (raynaney@gmail.com) or Abdallah El Ali (aea@cwi.nl), and they can share the Assets with you.

## Citation

Please cite our paper in any published work that uses this dataset as follows：
- Plain Text
```
Coming soon.
```
- BibTex
```
Coming soon.
```

## Unity Setup

Once you have made a copy of this repo, you can use Unity editor version 2020.3 to run it. This project was never intended to be 'built', and wa always run from the editor to allow easy monitoring of the console. This project was based on the Excite-O-Meter framework (see [here](https://sites.google.com/view/exciteometer/) and [here](https://github.com/luisqtr/exciteometer) for its documentation and [here](https://ieeexplore.ieee.org/document/9583798) for a paper about it). The 'main experiment' scene will not function unless there is an ECG stream detected from the Polar H10 monitor. In order to set up the sensor so that it can stream to Unity, see [this documentation](https://github.com/luisqtr/exciteometer/blob/main/docs/2_SetupDevices.md)*.

There are three modalities as part of the 'main experiment': an audio only condition, visual condition, and audio-visual condition. The order in which these modalities occur is set by the particpant ID, which automatically assigns the correct counterbalancing order. The default setting for number of trials in each condition is set at 15, but this can be changed under the `canvas -> heart` game object in the 'main practice' scene.

The scene order is set as follows: 

1) Start Practice Scene
2) Main Practice** 
3) Rate-Confidence Questions** 
4) Start Screen
5) Main Experiment***
6) HR-Confidence Questions***
7) Break Between Blocks****
8) Survey Scene

*For this experiment, we used a desktop computer to stream data from the sensor, and not the mobile option.

** 'Main Practice' and 'Rate-Confidence Questions' are shown for as many trial numbers that are set, where the default is set at 5, which can be changed under `canvas(1) -> circle`. So the participant would see a Main Practice scene, then the Rate-Confidence Questions scene repeated for the number of trials.

***'Main Experiment' and 'HR-Confidence Questions' scenes repeatedly alternate in the same way as the Main Practice and Rate-Confidence Questions scenes.

****The 'Break Between Blocks' scene occurs between each modality change

<!-- ## Guide to Counterbalancing

In order to avoid manually changing the modality order and whether the first heart rate is real or fake, counterbalanced modality order and real/fake starting condition is determined by the participant number. 

If the PID is divisible by 2, then the starting condition is real, so all even numbered participants have a real starting condition.
The modality ordering is determined by taking PID % 6, and using that number to index the list ["avc", "acv", "vac", "vca", "cav", "cva"]. -->

## Running the experiment

See [this document](https://docs.google.com/document/d/1pZU_3bVSRl4_6hC2f2UO7JVBU-rDykZ8SOhFMcOgvBA/edit?usp=sharing) for precise steps on how to run this experiment in its entirety.

## Troubleshooting

**Polar H10 Issues:** The Polar H10 stream may become disconnected during the experiment. If this happens during the 'Main Experiment' scene, then an error will be shown in the console stating that the ECG stream has become disconnected. Usually, this happens because the sensor has become dried out. To fix this, just rewet the sensor. As soon as ECG data starts streaming again, the heartbeat will begin again on its own, with no action needed from the experimentor.

**Unity Setup Issues:** If there is no headset connected to Unity through the Steam engine, then the program will not work. If SteamVR seems to be functioning as normal and the problem persists, you may have to re-download the SteamVR Plugin.

