# Mistral7B-HTML-Gen-figr

Welcome to the repository, where I've fine-tuned the [Mistral 7B](https://huggingface.co/mistralai/Mistral-7B-v0.1) model specifically for the generation of HTML code.

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcShSw0Ge2KIlcVBcRsNHaZBL-Z89PMBMWEFKQ&usqp=CAU)
#### **Objectives Addressed**

 1. Model Section.
 2. Data Preparation.
 3. Tokenization.
 4. Fine-Tuning with LoRA
 5. Evaluation
 6. API dev

##  Objective

The primary goal of this assignment was to fine-tune the Mistral 7B model for generating HTML code from natural language prompts.

## Dataset

I utilized the `jawerty/html_dataset` from Hugging Face Datasets, containing 43 examples of natural language prompts paired with corresponding HTML code.

## Model Selection and Architecture

- At the core of Mistral 7B lies a [Transformer architecture](https://datagen.tech/guides/computer-vision/transformer-architecture/#:~:text=The%20Transformer%20architecture%20uses%20an%20encoder-decoder%20structure%20that,previous%20time%20step%2C%20and%20generates%20an%20output%20sequence.), a fundamental component of modern language models. Nevertheless, it introduces several groundbreaking innovations that contribute to its exceptional performance. In comparison to [Llama](https://github.com/openlm-research/open_llama), it brings about some significant changes:
![enter image description here](https://cdn.labellerr.com/1%20mistral%207b/architecture.webp)
- The Mistral 7B model, a 7.3B parameter transformer with Grouped-query attention (GQA) and Sliding Window Attention (SWA), was selected for its optimal balance between performance and efficiency. GQA enhances inference speed, while SWA handles longer sequences effectively.


## Data Preparation

I carefully prepared the data by splitting it into training and testing sets, adding special tokens, padding, and masking. Token distribution visualizations were employed, experimenting with LangChain Recursive Splitter and SWA features to handle large token lengths in HTML code.

## Fine-Tuning with LoRA

The fine-tuning process involved the use of Low Rank Adaptation (LoRA), a parameter-efficient approach that outperformed full finetuning in certain cases. 
![enter image description here](https://miro.medium.com/v2/resize:fit:1400/1*rOW5plKBuMlGgpD0SO8nZA.png)

Leveraging the Hugging Face PEFT library, I set hyperparameters based on model documentation and employed the PyTorch Trainer class for efficient training. WandB was used for visualization and tracking during training.

## API Development

To facilitate user interaction with the fine-tuned model, I implemented an API using Flask. Users can input natural language queries, and the model will generate corresponding HTML code. This enhances the practical application of the model by making it accessible and user-friendly.

## Evalua**strong text**tion

The model's performance was evaluated using ROUGE scores (1, 2, L), perplexity, and visual inspection of generated HTML code. WandB facilitated result logging and comparison between different data preparation methods.

## Challenges Faced

Challenges included **GPU interruptions** during training in Colab, **handling large token lengths** in HTML codes, and the **complexity of tensor manipulation** and **training parameters**.

- **Token Distribution Visualizations**
  
![Token distribution ](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FA35Rv0zJFBdhdWgjEt16%2Fuploads%2FI3mJy0xUGCNDKwnjTICw%2Fimage.png?alt=media&token=8c277c51-dc77-4473-8b4b-07b55d48c073)

## Documentation
Check out the documentation at this link -> [Access Here👆](https://zaheer.gitbook.io/figr-tuning/)

## Conclusion

In conclusion, my journey from model selection to fine-tuning, evaluation, and API development has been both challenging and rewarding. Thank you for reading, and I hope you find this [Readme.md](https://github.com/Zaheer-10/Mistral7B-HTML-Gen-figr/README.md) was helpful and informative.

## License

This project is licensed under the terms of the MIT license. See the [LICENSE](https://opensource.org/license/mit/) file for details.
