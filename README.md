# Mobile Stable Diffusion

> This repository was forked from [https://github.com/apple/ml-stable-diffusion](https://github.com/apple/ml-stable-diffusion)


## Converting Models to CoreML


## Implementation of LCM Scheduler

The Latent Consistency Sheduler is added to the implementation in [Scheduler.swift](swift/StableDiffusion/pipeline/Scheduler.swift)



### First export the path to the compiled coreml models

```
export COREML_MODELS_PATH=<path_to_models>
```
replacing <path_to_models> with the absolute path to the models folder


### Then generate an image using
```
swift run StableDiffusionSample "a cat" --resource-path $COREML_MODELS_PATH --seed 123456 --disable-safety --compute-units cpuAndNeuralEngine --step-count 4 --output-path images --scheduler lcm --guidance-scale 1.0
```

On a macbook, the first time to loading the model may take a few minutes, and subsequent image generation should take a few seconds.

<p align="center">
  <img src="images/a_cat.123456.final.png" width="300" height="300"/>
</p>

The generated images will appear in the [images](images) folder, tagged with their name and random seed