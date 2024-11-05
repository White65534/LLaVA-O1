
 

# LLaVA-O1: Open Large Reasoning MLLMs Frameworks

**LLaVA-O1** is an open-source framework designed for training, inference, and evaluation of large reasoning models (MLLMs) using PyTorch and HuggingFace. It aims to streamline the development of robust multimodal language models by integrating efficient workflows with popular libraries.

## Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Getting Started](#getting-started)
- [Training](#training)
- [Inference](#inference)
- [Evaluation](#evaluation)
- [Contributing](#contributing)
- [License](#license)

## Features
- **Flexible Training Pipelines**: Support for various training modes including single-GPU, multi-GPU, and distributed training.
- **Inference with HuggingFace Integration**: Seamlessly conduct inference using HuggingFace’s model hub.
- **Extensive Evaluation**: Built-in metrics and evaluation tools for assessing model performance.
- **Multimodal Compatibility**: Designed to handle multimodal tasks, enabling diverse applications from text-only tasks to multimodal reasoning.

## Installation
To install and set up LLaVA-O1, you need to have Python 3.8+ and PyTorch installed. Follow these steps to set up the environment:

```bash
# Clone the repository
git clone https://github.com/your-username/LLaVA-O1.git
cd LLaVA-O1

# Create a virtual environment
python -m venv llava_env
source llava_env/bin/activate  # On Windows, use `llava_env\Scripts\activate`

# Install dependencies
pip install -r requirements.txt
```

### Additional Requirements
If you plan to use GPU support, ensure you have the appropriate CUDA version installed.

## Getting Started
After installation, you can quickly start by running a simple inference or training example. Here’s how:

1. **Model Configuration**: Define your model configuration by editing the `config.yaml` file.
2. **Dataset Preparation**: Organize your data under the `data/` directory, following the example dataset structures provided in `examples/`.

### Example Inference
To run a simple inference with LLaVA-O1, use the following command:

```bash
python scripts/inference.py --config config.yaml --input data/sample_input.txt
```

## Training
LLaVA-O1 supports both single-GPU and distributed training using PyTorch. To train a model, modify the training configurations in `config.yaml` and then run:

```bash
python scripts/train.py --config config.yaml
```

### Distributed Training
For distributed training, use:

```bash
torchrun --nproc_per_node=NUM_GPUS scripts/train.py --config config.yaml
```

Replace `NUM_GPUS` with the number of GPUs available for training.

## Inference
After training, you can perform inference on new data. Specify the model path in `config.yaml` and run:

```bash
python scripts/inference.py --config config.yaml --input data/inference_data.txt
```

## Evaluation
To evaluate the model on a test set, use the evaluation script:

```bash
python scripts/evaluate.py --config config.yaml --input data/test_data.txt
```

### Supported Evaluation Metrics
- **Accuracy**
- **Precision/Recall/F1 Scores**
- **Task-Specific Metrics** (e.g., BLEU, ROUGE for text, etc.)

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch with your feature/bugfix.
3. Submit a pull request with a clear description of your changes.

## License
This project is licensed under the MIT License. See the `LICENSE` file for more information.

 
