<div align="center">
  <img src="assets/klaralabs.png" alt="Klara Labs" width="200"/>
  <br>
  <br>
  <img src="assets/detectivebird.jpeg" alt="Mascotte" width="200" style="border-radius: 20px; margin: 20px 0;"/>

  # Klarity 

  _Understand what your model is thinking_
</div>

## 🎯 Overview

Klarity is a powerful tool for understanding the uncertainty in language model outputs. Unlike traditional confidence scores, Klarity combines advanced analysis with LLM-powered insights to give you a clear understanding of your model's behaviour.

### 🔍 What sets Klarity apart?

- **Semantic Analysis**: Goes beyond raw probability distributions to understand the meaning-based uncertainty
- **Intelligent Insights**: LLM-powered analysis of semantic patterns
- **Actionable Recommendations**: Get actionable suggestions for handling uncertainty cases

## 🤖 Supported Models

| Model | Type | Status | Notes |
|-------|------|--------|--------|
| GPT-NeoX | 20B | ✅ Tested | Full semantic analysis support |
| LLaMA 2 | 7B | ✅ Tested | Optimized cluster analysis |
| Qwen | 0.5B | ✅ Tested | Fast analysis, great for testing |

> **Note**: More models are being tested and will be added to the list. If you'd like to contribute by testing additional models, please submit a PR!

## 🚀 Quick Start

Install directly from GitHub:
```bash
pip install git+https://github.com/yourusername/klarity.git
```

Start analyzing your model:
```python
from transformers import AutoModelForCausalLM, AutoTokenizer
from klarity import UncertaintyEstimator

# Load your model
model_name = "mistralai/Mistral-7B-v0.1"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(model_name)

# Initialize Klarity
estimator = UncertaintyEstimator()

# Get semantic insights with explanations
response = estimator.estimate(
    "What is the best programming language for AI?", 
    model, 
    tokenizer
)

# Access structured insights
print(f"Semantic Entropy: {response.metrics.semantic_entropy:.4f}")
print(f"Cluster Quality: {response.metrics.cluster_quality:.4f}")
print(f"Number of Semantic Clusters: {response.metrics.n_clusters}")

# Get LLM-powered analysis
print("\nInsights:")
print(f"Confidence Level: {response.insights.confidence_level}")
print(f"Primary Factor: {response.insights.primary_factor}")
print("\nRecommendations:")
for rec in response.insights.recommendations:
    print(f"- {rec}")
```

Example Output:
```
Semantic Entropy: 0.8234
Cluster Quality: 0.7645
Number of Semantic Clusters: 3

Insights:
Confidence Level: Medium
Primary Factor: Multiple valid programming paradigms

Recommendations:
- Consider specifying the AI domain (ML, NLP, Computer Vision)
- Add context about scalability requirements
- Clarify if looking for research or production use case
```

## 💡 Use Cases

### Model Analysis
- Understand when your model is considering multiple valid perspectives
- Get explanations for uncertainty in specific domains
- Receive suggestions for improving prompt clarity

### Quality Assurance
- Detect and understand edge cases with LLM-powered insights
- Monitor coherence with explained metrics
- Get actionable feedback for handling ambiguous cases

### Model Improvement
- Use semantic insights and recommendations for fine-tuning
- Understand patterns in model responses
- Get suggestions for training data improvements

## 🤝 Contributing

We welcome contributions! Whether it's:
- Testing with new models
- Improving semantic analysis
- Enhancing LLM insights
- Sharing use cases

See our [Contributing Guide](CONTRIBUTING.md) for details.

## 📝 License

MIT License. See [LICENSE](LICENSE) for more information.

## 📫 Community & Support

- [GitHub Issues](https://github.com/klaralabs/klarity/issues) for bugs and features
- [GitHub Discussions](https://github.com/klaralabs/klarity/discussions) for questions and community discussions