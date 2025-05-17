# **Flux-Icon-Kit-LoRA**
![icon pack.png](https://cdn-uploads.huggingface.co/production/uploads/65bb837dbfb878f46c77de4c/G_QXbbtYT1YFflykerj-m.png)
## Image Gallery

<p align="center">
  <img src="images/1.png" width="30%" alt="Image 1">
  <img src="images/2.png" width="30%" alt="Image 2">
  <img src="images/3.png" width="30%" alt="Image 3">
</p>
<p align="center">
  <img src="images/4.png" width="30%" alt="Image 4">
  <img src="images/5.png" width="30%" alt="Image 5">
  <img src="images/6.png" width="30%" alt="Image 6">
</p>


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
