# Transformer-Based C++ Code Generator

We implemented a Transformer model inspired by Google Brain’s paper [*Attention Is All You Need*](https://arxiv.org/abs/1706.03762), trained entirely at the character level to generate valid and meaningful C++ code.

This project generates code with structure, variable usage, and correct syntax — purely by predicting one character at a time, without specifying any explicit tokenization or syntax awareness.

---

## Key Features

- Built Transformer from scratch with:
  - Token embeddings
  - Positional encoding
  - Multi-head self-attention
  - Layer normalization and residuals
- Character-level training on raw C++ source code
- Learns syntax, structure, and logic without explicit rules
- Generates valid C++ code from incomplete inputs
- Modular and extensible architecture

---

## Example

**Input Prompt:**
```cpp
int main() {
    int n =
```

**Generated Output:**
```cpp
int main() {
    int n = 5;
    for (int i = 0; i < n; i++) {
        cout << i << endl;
    }
    return 0;
}
```

---

## Repository Structure

```
.
├── src/
│   ├── model.py              # Transformer model definition
│   ├── train.py              # Training script
│   └── generate.py           # Code generation script
├── data/
│   └── cpp_code_dataset.txt  # Raw C++ training data
├── checkpoints/
│   └── model_weights.pth     # Trained model parameters
├── examples/
│   ├── input_prompt.cpp      # Sample prompt
│   └── generated_output.cpp  # Model-generated code
├── notes/
│   ├── theory.pdf            # Handwritten notes on Transformer theory
│   └── research_summary.md   # Summary and learnings
├── requirements.txt
└── README.md
```

---

## Getting Started

### Install Dependencies
```bash
pip install -r requirements.txt
```

### Train the Model
```bash
python src/train.py --input data/cpp_code_dataset.txt --epochs 20
```

### Generate Code
```bash
python src/generate.py --prompt "int main() {" --output examples/generated_output.cpp
```

---

## Customization
- You can use this model to predict any form of data which can use previous stream of output to predict the next output (e.g.custom chatbot)
- You just have to replace the training dataset (`cpp_code_dataset.txt`) with training dataset.
- The architecture is modular and can be extended with more layers, token-level training, or other features.
- You can fine-tune the model or export it for downstream use cases like code completion tools.

---

## Included Materials

- Full source code with training and generation logic
- Raw training data
- Our handwritten notes and theoretical understanding
- Trained model weights for quick testing
- Example inputs and generated outputs

---

## Future Directions

- Train on larger datasets from open-source C++ projects
- Add token-level processing for better long-term context
- Customize on other data prediction sets for exteded practical use.
- Integrate evaluation metrics like perplexity or BLEU
- Build a simple web UI for interactive use

---

## Authors

- Purab
- Khushhal
- Tanmay
- Aadi


