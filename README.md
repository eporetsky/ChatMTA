# ChatMTA

Using Large Language Model (LLM) for extraction and biocuration of genetic mapping data from manuscripts.

# Introduction

Curated resources at centralized repositories provide high-value service to users by enhancing data veracity. Curation, however, comes with a cost, as it requires dedicated time and effort from personnel with deep domain knowledge. We investigate the performance of a Large Language Model (LLM), ChatGPT, in extracting and presenting data from genetic mapping studies. In order to accomplish this task, we used a small set of journal articles on wheat genetics, focusing on traits, such as salinity tolerance and disease resistance, that are becoming more important as climate change is continuously impacting agriculture globally. The 21 papers were then curated by a professional curator for the GrainGenes database (https://wheat.pw.usda.gov). In parallel, we developed a ChatGPT-based retrieval-augmented generation (RAG) question-answering (QA) system and compared how ChatGPT performed in answering questions about traits and quantitative trait loci (QTLs). Despite their limitations, LLMs demonstrated a potential to extract and present information to curators and users of biological databases, as long as users are aware of potential inaccuracies and the possibility of incomplete information extraction.

# Data analysis

The repository contains the input and output data used to generate the results and figures. The text of the 21 manuscripts used in this work were parsed using [SciPDF](https://github.com/titipata/scipdf_parser), which requires GROBID process to be available in the background. The LLM analysis of the parsed PDFs was conducted using the [FAISS](https://faiss.ai/) database and [LangChain](https://www.langchain.com/) package. 

# Instructions

## Prepare environment

Create the conda environment and install all the required packages to the code in the notebooks.

```
conda create --name chatmta python=3.10 anaconda::jupyter
conda activate chatmta
pip install -r requirements.txt
jupyter notebook
```

## Decompress the `data.zip` file

Either manually or run the command `unzip data.zip`. Three unzipped folders should be located in the repository base folder.

## Getting an OpenAI key

Running the prompts using the OpenAI ChatGPT models requires an API key that can be obtained through: https://platform.openai.com/docs/overview

The unqieu API key can then be used to replace the key in the beginning of each notebook: `os.environ['OPENAI_API_KEY'] = 'key'`

## Run notebooks

Each notebook contains the code to generate the results and figures used in the manuscript. The plots can be reproduced without using the OpanAI ChatGPT models through LangChain. Note that running the LLM prompts available in the notebooks is likely to generate results that do not perfectly match the reported results.

# Citation

In review.