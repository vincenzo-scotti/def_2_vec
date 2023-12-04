# Def2Vec

The codebase for the paper "[Def2Vec: Extensible Word Embeddings from Dictionary Definitions](https://www.overleaf.com/read/mjqknffjfhkw)".
For all the references, contributions, and credits, please refer to the paper.

This code was initially developed as part of the M.Sc. Thesis in Computer Science and Engineering "[Def2Vec: a model to extract word embeddings from dictionary definitions](https://www.politesi.polimi.it/handle/10589/179715)".
The M.Sc. degree was released by the Dipartimento di Elettronica, Informazione e Bioingengeria  ([DEIB](https://www.deib.polimi.it/eng/home-page)) of the Politecnico di Milano University ([PoliMI](https://www.polimi.it)).

## Pre-trained models

We release pre-trained models learned from the [English Wikitionary](https://en.wiktionary.org/wiki/Wiktionary:Main_Page).
The pre-trained models is compatible with the *KeyedVectors* of the [Gensim API](https://radimrehurek.com/gensim/) (see example below).
The models are available at the following links: 

| Model size | Text file                                                                                                                                 | Gensim KV file                                                                                                                            |
|------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 50         | [download](https://polimi365-my.sharepoint.com/:u:/g/personal/10451445_polimi_it/EaI8ormefBlIoQB-1YWH22YBTD0rEtPbaD11YkMMNqlKxg?e=qLAMmA) | [download](https://polimi365-my.sharepoint.com/:u:/g/personal/10451445_polimi_it/ERJlBEE6EsNLmyK9t2nsCsEBR5L9cKsr_s9xXz3YIlcF6w?e=9poPf7) |
| 100        | [download](https://polimi365-my.sharepoint.com/:u:/g/personal/10451445_polimi_it/EbYQNGrfPuBPhEXA-EjPL7IBmM0XqB_ZYewU1nj5p3jHRQ?e=Pyb0ac) | [download](https://polimi365-my.sharepoint.com/:u:/g/personal/10451445_polimi_it/EcD5S6HqE0NDmgfDTADyc9gBHlkRoRofGvgV8cVOGJ2ISw?e=ayr8e5) |
| 300        | [download](https://polimi365-my.sharepoint.com/:u:/g/personal/10451445_polimi_it/EfQqgCR4fxxFoWWgw3YSYYIBAKq20vtObQNpjiJ1GiyQMA?e=PAncqK) | [download](https://polimi365-my.sharepoint.com/:u:/g/personal/10451445_polimi_it/EV4dqNoPQRFBnRh8TqXeh0IBtdD83314hQ-rkC8h5nucVQ?e=yEGJ0S) |

> [!NOTE]
> 
> Only the embedding part of the Def2Vec models is available at the moment (refer to the paper for further details).

## Example

Here follow an example of:
- model loading
- word embedding extraction
- sequence embedding extraction

```python
import numpy as np
from nltk.tokenize import word_tokenize
from gensim.models import KeyedVectors


# Path to the Gensim KV file
path = './def2vec_en_wikitionary_50.kv'

# Load model
def2vec = KeyedVectors.load(path)
# Embed single word
embedding = def2vec['vector']
# Embed word sequence
sequence_embedding = np.vstack([
    def2vec[token.lower()] for token in word_tokenize('Vector semantics is cool!')
])
```

For further examples, refer to the Jupyter Notebook available in this repository.

## Cite work

If you are willing to use our model, please cite our work through the following BibTeX entry:

```bibtex
@inproceedings{morazzoni-etal-2023-def2vec,
  author    = {Irene Morazzoni and
               Vincenzo Scotti and
               Roberto Tedesco},
  title     = {{Def2Vec}: Extensible Word Embeddings from Dictionary Definitions},
  booktitle = {6th International Conference on Natural Language and Speech Processing,
               {ICNLSP} 2023, Trento, Italy, December 16-17, 2023},
  publisher = {Association for Computational Linguistics},
  year      = {2023}
}
```

## Acknowledgments

- Irene Morazzoni ([irene.morazzoni@mail.polimi.it](mailto:irene.morazzoni@mail.polimi.it))
- Vincenzo Scotti ([vincenzo.scotti@polimi.it](mailto:vincenzo.scotti@polimi.it))
- Roberto Tedesco ([roberto.tedesco@polimi.it](mailto:roberto.tedesco@polimi.it))
