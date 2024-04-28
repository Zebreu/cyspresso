# CysPresso
A machine learning approach to predict the recombinant expressibility of cysteine-dense peptides in mammalian cells based on their primary sequence, compatible with multiple types of deep learning protein representations.

## Associated paper

CysPresso: Prediction of cysteine-dense peptide expression in mammalian cells using deep learning protein representations. BioRxiv link: https://www.biorxiv.org/content/10.1101/2022.09.17.508377v1

The raw data (protein representations) used in this work can be obtained here: https://huggingface.co/datasets/TonyKYLim/CysPresso/tree/main

## Getting started

You can try out any sequence using the BringYourOwnSequences-CysPressoESM.ipynb notebook in a colab environment.

Our method's notebook can be opened through Colab at https://githubtocolab.com/Zebreu/cyspresso/blob/main/CysPresso.ipynb where you can explore both the dataset and the methodology we used for this study. You can upload CDPs.csv provided in this repo and any embeddings you generated to the colab workspace to run the notebook. 

## Embedding generation

### Colabfold
You can use https://github.com/sokrypton/ColabFold to generate embeddings saved as npy files in the colab workspace. In the "Run Prediction" code cell, use the following arguments:
```
run(
    queries=queries,
    result_dir=result_dir,
    use_templates=use_templates,
    custom_template_path=custom_template_path,
    use_amber=use_amber,
    msa_mode=msa_mode,    
    model_type=model_type,
    num_models=5,
    num_recycles=num_recycles,
    model_order=[1, 2, 3, 4, 5],
    is_complex=is_complex,
    data_dir=Path("."),
    keep_existing_results=False,
    recompile_padding=1.0,
    rank_by="auto",
    pair_mode=pair_mode,
    stop_at_score=float(100),
    prediction_callback=prediction_callback,
    save_single_representations=True,
    save_pair_representations=True,
    dpi=dpi
)
```
### OpenFold
It is also possible is to use OpenFold with our modified notebook at https://githubtocolab.com/Zebreu/cyspresso/blob/main/openfoldrepresentations.ipynb.
Cells after the prediction cell show where to find the embeddings, e.g. `all_results['results']['single']`.
OpenFold might generate predictions more slowly than ColabFold.

### References
The cysteine-dense peptide database was modified from [Correnti, CE *et al.* Nat Struct Mol Biol. 2018](https://rdcu.be/cVOc2).
