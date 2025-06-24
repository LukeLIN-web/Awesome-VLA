# Awesome Vision-Language-Action Models

A curated list of Vision-Language-Action (VLA) models, benchmarks, and datasets for robotic manipulation and embodied AI.

## Table of Contents
- [VLA Models](#vla-models)
- [Benchmarks](#benchmarks)
- [Datasets](#datasets)

## VLA Models

### SpatialVLA
- **Paper**: https://arxiv.org/abs/2501.15830
- **Status**: ✅ Successfully reproduced the results in the paper
- **Notes**: Code is very clean. using PaliGemma 3B LLM, tokenizer bin action head.

--- 

### OpenVLA-OFT
- **Website**: https://openvla-oft.github.io
- **Status**: ✅ Successfully reproduced the results in the paper
- **Notes**: using llama2-7B LLM, mlp or diffusion action head.

---

### Pi0

- Achieves ~94% average accuracy on the LIBERO benchmark.  
  [Reference](https://github.com/SpatialVLA/SpatialVLA/issues/5#issuecomment-2668021101)  
- **Model details**: Uses **PaliGemma-3B** as the LLM and **DiT** for the action head.

#### Real-world observations

1. Performs well with only **80 samples**, fine-tuned on **A100**.
2. Scales with **3–4k high-quality samples**. Successful fine-tuning on  
   [Hugging Face model](https://huggingface.co/lerobot/pi0) using:
   - **bf16**
   - **batch size = 12**
   - **~70GB VRAM**
   - **multi-machine** setup
   - **DeepSpeed ZeRO-2** (no offloading)  
   Training from scratch fails when data is limited.
3. `pi0-fast` variant works effectively in this [paper](https://arxiv.org/pdf/2506.09937).  
   Project site: [Physical Intelligence – pi0-fast](https://www.physicalintelligence.company/research/fast)

---

### ACT

- **Paper**: [ACT: Adaptive Curriculum for Robot Policy Learning](https://arxiv.org/abs/2304.13705)  
- **Note**: Can produce smooth grasping behavior with as few as **70 demonstrations**.

---

### Diffusion Policy

- GitHub: [real-stanford/diffusion_policy](https://github.com/real-stanford/diffusion_policy)  
- Works effectively in this [paper](https://www.arxiv.org/pdf/2506.16211)





---

*Note: There are hundreds of VLA models available. This list focuses on models that I have personally tested or for which reproduction results have been reported somewhere.*

## Benchmarks

### ✅ Tested Benchmarks
- **LIBERO**
  - **Website**: https://libero-project.github.io/main.html
  - **Reference**: https://github.com/moojink/openvla-oft/blob/main/experiments/robot/libero/run_libero_eval.py
- **SimplerEnv**
  - **Enhanced Repository**: https://github.com/DelinQu/SimplerEnv-OpenVLA , This repository provides additional scripts and utilities to help you run the benchmark

### 🔄 Benchmarks to Try
- **RLBench**: 
  - Repository: https://github.com/stepjam/RLBench
- **CALVIN**: 
  - Repository: https://github.com/mees/calvin
- **Meta-World**: 
  - Website: https://meta-world.github.io/
- **RoboTwin**: 
  - Repository: https://github.com/robotwin-Platform/RoboTwin
- **RoboCasa**: 
  - Paper: https://arxiv.org/abs/2406.02523v1
  - Repository: https://github.com/robocasa/robocasa

## Datasets

### ✅ Tested Datasets

#### Open X-Embodiment
- **Website**: https://robotics-transformer-x.github.io/
- **Code**: https://github.com/kpertsch/rlds_dataset_mod
- **Total Size**: ~2.0TB

**Dataset Breakdown:**
```
1.2T    ./fmb_dataset
126G    ./taco_play
128G    ./bc_z
124G    ./bridge_orig                                            # 2.1M samples
140G    ./furniture_bench_dataset_converted_externally_to_rlds
98G     ./fractal20220817_data                               # 3.78M samples
70G     ./kuka
22G     ./dobbe
20G     ./berkeley_autolab_ur5
16G     ./stanford_hydra_dataset_converted_externally_to_rlds
16G     ./utaustin_mutex
14G     ./austin_sailor_dataset_converted_externally_to_rlds
13G     ./nyu_franka_play_dataset_converted_externally_to_rlds
11G     ./toto
8.0G    ./austin_sirius_dataset_converted_externally_to_rlds
5.9G    ./iamlab_cmu_pickup_insert_converted_externally_to_rlds
4.5G    ./roboturk
3.3G    ./berkeley_cable_routing
3.2G    ./viola
3.0G    ./jaco_play
2.5G    ./berkeley_fanuc_manipulation
1.2G    ./austin_buds_dataset_converted_externally_to_rlds
510M    ./cmu_stretch
263M    ./dlr_edan_shared_control_converted_externally_to_rlds
110M    ./ucsd_kitchen_dataset_converted_externally_to_rlds
```

### 🔄 Datasets to Try
- **CALVIN**: 
  - Repository: https://github.com/mees/calvin
  - Size: ~1.1TB
- **RoboTwin**: 
  - Repository: https://github.com/robotwin-Platform/RoboTwin
- **Droid**
  - **Website**: https://droid-dataset.github.io/
  - **Size**: ~1.7TB

## Contributing

We welcome contributions! Please feel free to:
- Add new VLA models you've tested
- Share benchmark that is easy to use
- Report dataset experiences
- Submit pull requests or issues

## Contact

Feel free to send us pull requests, issues, or [email](mailto:1263810658@qq.com) to share your reproduction experience!
