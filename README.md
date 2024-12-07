---
tags:
- text-to-image
- lora
- diffusers
- template:diffusion-lora
widget:
- text: 'Icon Kit, An animated image of a yellow and purple jar. The jar has a white lightning bolt on it. The background is a bright blue.'
  output:
    url: images/1.png
- text: 'Icon Kit, An eye-level view of a vibrant orange jack-o-lantern against a backdrop of a deep blue sky. The pumpkins face is angled towards the left, with a black outline around it. The eyes are squinted with white lines, creating a striking contrast with the orange and yellow of the pumpkin. The orange is adorned with black lines, adding a pop of color to the scene.'
  output:
    url: images/2.png
- text: 'Icon Kit, An animated image of a red canister with a black cap on the top. The canister has a black stripe on the side and a yellow hose attached to the cap. The background is a bright blue color.'
  output:
    url: images/3.png
- text: 'Icon Kit, Captured from a low-angle perspective on a vibrant blue backdrop, a black and white graphic is depicted in the center of the frame. The graphic features a black round object with a white outline of a skull in the middle of it. The skull has three black circles around it, and a black circle around it. A small orange carrot is sticking out of the top of the object, adding a pop of color to the scene.'
  output:
    url: images/4.png
- text: 'Icon Kit, An animated image of a rustic brown leather satchel with a brass buckle. The bag has a small green vine growing out of its side pocket. The background is a gradient of light green and beige, adding an earthy vibe.'
  output:
    url: images/5.png
- text: 'Icon Kit, A side-view animated image of a flaming red and orange torch with flickering flames. The handle is wooden with black iron bands. The background is a dark, smoky gray, making the flames stand out vividly.'
  output:
    url: images/6.png
base_model: black-forest-labs/FLUX.1-dev
instance_prompt: Icon Kit
license: creativeml-openrail-m
---
![icon pack.png](https://cdn-uploads.huggingface.co/production/uploads/65bb837dbfb878f46c77de4c/G_QXbbtYT1YFflykerj-m.png)

<Gallery />

# Model description for Flux-Icon-Kit-LoRA

Image Processing Parameters 

| Parameter                 | Value  | Parameter                 | Value  |
|---------------------------|--------|---------------------------|--------|
| LR Scheduler              | constant | Noise Offset              | 0.03   |
| Optimizer                 | AdamW  | Multires Noise Discount   | 0.1    |
| Network Dim               | 64     | Multires Noise Iterations | 10     |
| Network Alpha             | 32     | Repeat & Steps           | 25 & 3100 |
| Epoch                     | 20   | Save Every N Epochs       | 1     |

    Labeling: florence2-en(natural language & English)
    
    Total Images Used for Training : 40 [ Raw 8-bit ]

## Best Dimensions & Inference

| **Dimensions** | **Aspect Ratio** | **Recommendation**       |
|-----------------|------------------|---------------------------|
| 1280 x 832      | 3:2              | Best                     |
| 1024 x 1024     | 1:1              | Default                  |

### Inference Range

- **Recommended Inference Steps:** 30–35

## Setting Up
```python
import torch
from pipelines import DiffusionPipeline

base_model = "black-forest-labs/FLUX.1-dev"
pipe = DiffusionPipeline.from_pretrained(base_model, torch_dtype=torch.bfloat16)

lora_repo = "strangerzonehf/Flux-Icon-Kit-LoRA"
trigger_word = "Icon Kit"  
pipe.load_lora_weights(lora_repo)

device = torch.device("cuda")
pipe.to(device)
```
## Trigger words

You should use `Icon Kit` to trigger the image generation.

## Download model

Weights for this model are available in Safetensors format.

[Download](/strangerzonehf/Flux-Icon-Kit-LoRA/tree/main) them in the Files & versions tab.

---
