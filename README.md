
# Fine-tuning Llama-7B Model

This repository contains the code and data for fine-tuning a Llama-7B model on a dataset containing user inputs and mid-journey prompts as responses.

## TESTIMONIALS

#### User Input: midjourney prompt for a retro-futuristic spaceship with organic shapes and bright colors

<img src="https://github.com/Naveen-Reddy55/Fine-Tuning-Fine-Tuning-Llama-2-7B-for-creating-midjourney-prompt/assets/71924097/0ac7607f-b097-420e-a3a7-5fbd015bafc6" alt="1" width="300"/>

<img src="https://github.com/Naveen-Reddy55/Fine-Tuning-Fine-Tuning-Llama-2-7B-for-creating-midjourney-prompt/assets/71924097/3b232be3-842b-4430-ab20-a510c53d582e" alt="3" height="300" width="400"/>

<img src="https://github.com/Naveen-Reddy55/Fine-Tuning-Fine-Tuning-Llama-2-7B-for-creating-midjourney-prompt/assets/71924097/fd201b68-9e7f-43bf-a4dc-edd4ffec91fd" alt="2" width="300"/>

## Dataset

The dataset used for fine-tuning the model is stored in a variable named `fine_tuning_data`. It contains three columns: `User`, `Prompt`, and `Text`.

The `User` column contains the user inputs, while the `Prompt` column contains the corresponding mid-journey prompts. The `Text` column is generated using the following template: `### Instruction: <USER PROMPT> ### Response: <RESPONSE / MID-JOURNEY PROMPTS `

This template adds special tokens `### Instruction:` and `### Response:` to the user input and mid-journey prompt, respectively. These special tokens are used by the model to distinguish between the instruction and response parts of the text.

## Fine-tuning

The Llama-7B model is fine-tuned on the `fine_tuning_data` dataset using standard techniques for fine-tuning language models. The fine-tuned model can then be used to generate mid-journey prompts given a user input.
## Training procedure


The following `bitsandbytes` quantization config was used during training:
- load_in_8bit: False
- load_in_4bit: True
- llm_int8_threshold: 6.0
- llm_int8_skip_modules: None
- llm_int8_enable_fp32_cpu_offload: False
- llm_int8_has_fp16_weight: False
- bnb_4bit_quant_type: nf4
- bnb_4bit_use_double_quant: True
- bnb_4bit_compute_dtype: bfloat16
### Framework versions


- PEFT 0.4.0
