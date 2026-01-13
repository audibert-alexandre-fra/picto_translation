# Picto Grammar Project

Ce projet nécessite **Python 3.9** et **Git LFS** pour fonctionner correctement.

## Prérequis

* Python 3.9 installé
* Git LFS installé et configuré pour gérer les gros fichiers :

```bash
git lfs install
git lfs pull
```

## Installation

1. **Cloner le projet**

```bash
git clone <URL_DU_PROJET>
cd <NOM_DU_REPO>
```

2. **Modifier le fichier `.env`** pour correspondre à votre configuration, particulièrement :

```bash
export PYTHONPATH=$PYTHONPATH:/home/getalp/audibeal/Bureau/picto_datasets/picto_grammar/nwsd/src
```

3. **Installer les dépendances dans un environnement virtuel Python 3.9**

```bash
python3.9 -m venv venv39
source venv39/bin/activate
pip install uv
uv sync --active
```

## Mise en place des variables d'environnement

Exécutez le script suivant pour configurer les variables nécessaires :

```bash
./set_environement.sh
```

## Lancer le code

Pour exécuter le script principal, utilisez la commande suivante :

```bash
python src/grammar.py \
    --wn_file "data/dico/index.sense" \
    --no_transl "data/dico/no_translation.csv" \
    --wsd "data/wsd_model/" \
    --lexicon "data/dico/lexicon.csv" \
    --data "examples/input.csv" \
    --out "examples/out.csv" \
    --tags "data/dico/tags.csv"
```
