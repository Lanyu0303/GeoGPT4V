# GeoGPT4V: Enhancing Multi-modal Large Language Models' Geometric Abilities through Geometric Image Generation.

This repository contains the code and data for the paper titled "GeoGPT4V: Enhancing Multi-modal Large Language Models' Geometric Abilities through Geometric Image Generation."


## Install

1. Clone this repository.

   ```shell
   git clone xxx
   cd xxx
   ```

2. Install Package.

   ```shell
   conda create -n ggeo python=3.10 -y
   conda activate ggeo
   pip install -r requirements.txt
   ```

3. Install Wolfarm engine. Please follow its [offical tutorial](https://support.wolfram.com/45743).

## Usage

### Data Preparation

1. Download following open-source datasets or use your own datasets:

   1. [Geometry3K](https://lupantech.github.io/inter-gps/)
   2. [GeoQA](https://github.com/chen-judge/GeoQA)
   3. [UniGeo](https://github.com/chen-judge/UniGeo)

2. Transform the dataset into the following format and save it as a jsonline file:

   ```
   # multi-choice quetion example
   {"id": 1, "question": "For the pair of similar figures, find the area of the green figure.", "choices": ["20.4", "28.6", "56.0", "78.4"], "answer": "D", "image": "image path"}
   
   # open-ending quetsion example
   {"id": 2, "question": "Prove that △ABC is congruent to △DEF.", "answer": "Because AB = DE, BC = EF, and ∠ABC is equal to ∠DEF, △ABC is congruent to △DEF.", "image": "image path"}
   ```

3. [optional] If you are using your own dataset, please modify the function 'construct_prompt'  in './pipeline/gen_instruction_mp.py'.

### Data Generation

Run the scripts in the following order, remember to modify the dataset path and API key in the scripts.

1. sh scripts/gen_instruction_gpt4v_mp.sh
2. sh scripts/gen_image_mp.sh
3. sh scripts/rerank_gp4v_mp.sh
4. sh scripts/filter.sh

## Train

You can use following models' offical training code or use your own code. Please transform the GeoGPT4V dataset into the required format for model training.

1. [LLaVA](https://github.com/haotian-liu/LLaVA)
2. [ShareGPT4V](https://sharegpt4v.github.io/)
3. [InternVL-Chat](https://github.com/OpenGVLab/InternVL)

## GeoGPT4V Dataset

GeoGPT4V dataset is comming soon.

## Model Zoo

The checkpoints are comming soon.
