<div align="center">
  <br>
  <h1>WE4LKD</h1>
  <strong>Word Embeddings For Latent Knowledge Discovery</strong>
</div>
<br>

<div align="center">
  <br>
  <a href="https://doi.org/10.1016/j.eswa.2024.123566" target="_blank">
    <h2>Accelerating Discoveries in Medicine using Distributed Vector Representations of Words</h2>
  </a>
  <strong>Berto, Matheus V. V.; De Freitas, Breno L.; Scarton, Carolina E.; Neto, João A. M.; Almeida, Tiago A.</strong><br>
</div>

This study aims to extend a recently proposed strategy by combining different unsupervised models to accelerate discoveries in medicine. Distributed vector representations of words were trained on a large corpus of medical papers related to Acute Myeloid Leukemia (AML), a highly malignant form of cancer, and show that established therapies could be developed years before their first proposal. The results open new avenues toward faster medical discoveries through more effective drug and gene testing, enabling better treatments to promote a healthier, prolonged life for patients.

Starting from 1963 - the first explicit occurrence of AML in our corpus - we generated yearly prediction rankings for a set of 21 target compounds. We then calculated the percentage of these predicted AML treatments later reported in the literature, considering only the compounds in the top-3 predictions (orange curve) or not (blue curve). Using only the top-3 predictions would accelerate the percentage discovery of treatments up to 2.3x five years after the first predictions compared to random testing drugs.

<div align="center">
  <img src="/data/w2v_percentage_reported_top3_and_all.jpg" width="60%">
</div>

Finally, our models were able to identify and suggest testing of some of the currently known compounds used to treat AML up to 11 years before they were explicitly mentioned in the literature, as illustrated below. The remainder of this repository describes the evolution of the project.

<div align="center">
  <img src=/data/final_results.png>
</div>

## Table of Contents

- [Contributing](#contributing)
- [Built With](#built-with)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Usage](#usage)
  - [Streamlit web app](#streamlit-web-app)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact)
- [Citation](#citation)
- [References](#references)

## Contributing

We encourage you to contribute to our project! Please check out the
[Issued](https://github.com/matheusvvb-19/WE4LKD-leukemia_w2v/issues)
page.

## Built With

* [Gensim](https://radimrehurek.com/gensim/)
* [NLTK](https://www.nltk.org/)
* [Numpy](https://numpy.org/)
* [Plotly](https://plotly.com/)
* [Scikit-learn](https://scikit-learn.org/stable/)
* [Streamlit](https://streamlit.io/)

## Getting Started

This section provides a high-level quick start guide.

### Prerequisites

To use this project, you need to have Pyhton installed on your machine. This project used [Python version 3.6](https://www.python.org/downloads/release/python-360/). In addition, you will also need [Pip](https://pypi.org/project/pip/), the Python package manager to install the other requirements of the project.

Clone the repository
```sh
git clone https://github.com/matheusvvb-19/WE4LKD-leukemia_w2v.git
cd WE4LKD-leukemia_w2v/
```

Setup a Python virtual environment
```sh
# create venv
python3 -m venv venv
# activate venv
source venv/bin/activate
# install requirements
pip3 install --ignore-installed -r requirements.txt
```

### Usage

1. If you like, you can change the search phrases in the `/data/search_strings.txt` file
2. Run `crawler.py`
  ```sh
  mkdir results
  python3 crawler.py
  ```
or download, decompress, and place [this file](https://drive.google.com/file/d/1TY9AKbXYUNHKF6QYHGyJjB4SOypuhNkA/view?usp=sharing) into `/pubchem/`. If you do this, skip to step 5.

3. Execute the script `merge_txt.py`, this will generate the _.txt_ files with all articles between periods
  ```sh
  mkdir results_aggregated
  python3 merge_txt.py
  ```
4. Execute the script `/pubchem/clean_summaries.py`, which will clean the merged _.txt_ files
```sh
  python3 clean_summaries.py
```
5. Train the Word2Vec or FastText incremental models
```sh
  cd word2vec
  python3 train_yoy.py
```

### Streamlit web app

To complement this project, we developed two web applications using the Streamlit Python package. The Embeddings Viewer allows users to explore the vector space of our Word2Vec models by searching for specific tokens and analyzing their neighborhood, applying filters to refine the results if necessary.

[![Embedding Viewer](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://embedding-viewer.streamlit.app)

## Acknowledgements

This work was supported by the Brazilian agencies FAPESP (grant  2021/13054-8), Capes, and CNPq. The authors thank Priscila Portela Costa for helping conceptualize this project. We also thank the Computer Science Department from the University of Sheffield for recieving Matheus on his research internship for this project.

## Contact

Please do not exitate to contact us by any of the links below.
<div>
  <p>
    Matheus Vargas Volpon Berto,<br>
    Computer Science B.Sc. student, Federal University of São Carlos (UFSCar), Sorocaba, Brazil.
  </p>
  
  <a rel="nofollow noreferrer" href="https://www.linkedin.com/in/matheus-volpon/">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>

  <a rel="nofollow noreferrer" href="mailto:matheusvvb@hotmail.com">
    <img src="https://img.shields.io/badge/Microsoft_Outlook-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white"/>
  </a>

  <a rel="nofollow noreferrer" href="https://github.com/matheusvvb-19">
    <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
</div>

## Citation
```
@article{BERTO2024123566,
  title = {Accelerating discoveries in medicine using distributed vector representations of words},
  journal = {Expert Systems with Applications},
  volume = {250},
  pages = {123566},
  year = {2024},
  issn = {0957-4174},
  doi = {https://doi.org/10.1016/j.eswa.2024.123566},
  url = {https://www.sciencedirect.com/science/article/pii/S0957417424004317},
  author = {Matheus V.V. Berto and Breno L. Freitas and Carolina Scarton and João A. Machado-Neto and Tiago A. Almeida},
}
```

## References

* ["Unsupervised word embeddings capture latent knowledge from materials science literature", Nature 571, 95–98 (2019)](https://github.com/materialsintelligence/mat2vec)

[⬆ Back to Top](#Table-of-contents)
