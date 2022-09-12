# CysPresso

## Associated paper

BioArxiv link pending: 

## Getting started

The current notebook can be opened through Colab at https://githubtocolab.com/Zebreu/cyspresso/blob/main/criticaldifference.ipynb where you can explore both the dataset and the methodology we used for this study. You can upload knottins.csv and any embeddings you have to the colab workspace to run the notebook.

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
It is also possible is to use OpenFold with our modified notebook at https://githubtocolab.com/Zebreu/cyspresso/blob/main/openfoldrepresentations.ipynb
Cells after the prediction cell show where to find the embeddings, e.g. `all_results['results']['single']`
