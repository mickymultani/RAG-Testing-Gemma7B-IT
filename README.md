# Gemma 7B RAG Performance Testing

This repository is dedicated to testing the performance of Google's newly released open-source model, Gemma 7B, specifically tuned for instruction following. The focus is on Retrieval-Augmented Generation (RAG) to evaluate how well Gemma 7B can integrate and utilize external knowledge sources for generating answers.

## Overview

Gemma 7B, an instruction-tuned model, represents a significant step forward in natural language processing. This project aims to explore the model's capabilities in RAG tasks, leveraging a specific dataset for performance evaluation.

### Testing Setup

This RAG testing setup involves the following key components:

- **Indexing:** `llama-index`
- **Embedding Generation:** `FastEmbed`
- **Embedding Model:** `BAAI/bge-small-en-v1.5`

The testing framework requires the following library versions:

- `transformers=4.38.1`
- `llama-index=0.10.12`

### Data Document

I used the document "Hubble Focus: Strange New Worlds" as our primary data source for testing. The document is available [here](https://www.nasa.gov/wp-content/uploads/2022/06/hubble_focus_exoplanets_june2022.pdf?emrc=9057ef).

## Findings

Testing reveals that Gemma 7B's performance is impressively fast and generally accurate when questions are well-targeted, ensuring a good vector match. However, there are areas where the model falls short:

- The model struggles to infer conclusions based on the data presented in the document.
- It fails to answer questions based on information that, while present in the document, does not constitute the main flow of content. This issue could stem from the indexing process or the performance of the PDF parser.

### Considerations for Improvement

Given the challenges identified, exploring a new or different PDF parser may be beneficial to enhance the model's ability to comprehend and utilize the document's content fully.

## Repository Contents

- **Results:** Findings and performance evaluations are available in the `results` directory.
- **Notebooks:** The Jupyter notebook used for testing is accessible via this [Colab link](https://github.com/mickymultani/RAG-Testing-Gemma7B-IT/blob/main/RAG_Gemma7B_IT.ipynb).

### Running the Notebook

To run the notebook:

1. Ensure you have a HuggingFace access token. Set your token in the notebook to access the Gemma 7B model.
2. For optimal performance, I recommend using an `a100` GPU on Colab. However, a `t4` GPU should suffice for basic testing.

## Conclusion

This project offers valuable insights into the capabilities and limitations of Google's Gemma 7B model in RAG tasks. While the model demonstrates promising speed and accuracy in certain contexts, there's room for improvement, especially in data comprehension and utilization.

## Contributions

Contributions to this project are welcome! Whether it's suggesting new data documents for testing, improving the testing framework, or enhancing the parsing capabilities, your input can help refine the performance evaluation of Gemma 7B.

## License

This project is open-source and available under the [MIT License](LICENSE).

