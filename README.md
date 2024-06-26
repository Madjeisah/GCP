# GCP
**G**raph **C**ontrastive Multi-view Learning: A **P**re-training Framework for Graph Classification

## Pre-training
For pre-training task, run:
`python execute.py --logdir nc_ptrain.gcn --dataset nci1 --model gcn --augment_list random_walk_subgraph  node_attr_mask`

The model options are `gcn`, `graphsage` and `gin`.

Dataset: nci1, proteins, dd, enzymes, mutag, collab, imdb_multi, imdb_binary, reddit_multi and reddit_binary.

The augmentation choices are "node_dropping," "node_attr_mask," "edge_perturbation," "diffusion," and "random_walk_subgraph."

You can add other arguments like `--ptrain_percent 2.0`, which is the amount of data sample to use for pre-trained embeddings. And also change the number of workers depending on your CPU, like, `--num_workers 4`. The default is set to 8. 

## Downstream Tasks
For finetuning task, run:
`python classification.py --load nc_ptrain.gcn --logdir nc_ftune.gcn --dataset nci1 --model gcn`


