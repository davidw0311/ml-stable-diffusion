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