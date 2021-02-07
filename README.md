## UGRL
Official implementation of Robust Unsupervised Graph Representation Learning.

## Basics
- The main train/test code is in `IJCAI2021-3457/train.py`.
- If you want to see the UGRL layer in PyTorch Geometric `MessagePassing` grammar, refer to `IJCAI2021-3457/layers`.
- If you want to see hyperparameter settings, refer to `IJCAI2021-3457/args.yaml`.

## Requirements

  * PyTorch 1.4.0
  * Python 3.8
  
## Run

```text
python3 IJCAI2021-3457/train.py \
    --dataset-class Planetoid \
    --dataset-name Cora \
    --custom-key EV13NSO8
 
...

```

Default setting is 10 runs with different random seeds. If you want to change this number, change `num_total_runs` in the main block of `IJCAI2021-3457/train.py`.

### GPU Setting

There are three arguments for GPU settings (`--num-gpus-total`, `--num-gpus-to-use`, `--black-list`).
Default values are from the author's machine, so we recommend you modify these values from `IJCAI2021-3457/args.yaml` or by the command line.
- `--num-gpus-total` (default 4): The total number of GPUs in your machine.
- `--num-gpus-to-use` (default 1): The number of GPUs you want to use.
- `--black-list` (default: [1, 2, 3]): The ids of GPUs you want to not use.

If you have four GPUs and want to use the first (cuda:0),
```bash
python3 IJCAI2021-3457/train.py \
    --dataset-class Planetoid \
    --dataset-name Cora \
    --custom-key EV13NSO8 \
    --num-gpus-total 4 \
    --black-list 1 2 3
```

### Dataset (`--dataset-class`, `--dataset-name`)

| Dataset class   | Dataset name                  |Custom key    |
|-----------------|-------------------------------|--------------|
| Planetoid       | Cora                          |EV13NSO8      |
| Planetoid       | CiteSeer                      |EV13NSO8      |
| Planetoid       | PubMed                        |EV13NSO8      |
| WikiCS          | WikiCS                        |NE-500        |
| MyAmazon        | Photo                         |NE            |
| MyAmazon        | Computers                     |E             |
| MyCitationFull  | CoraFull                      |E             |
| MyCitationFull  | DBLP                          |E             |
| Crocodile       | Crocodile                     |EV13          |

### Other Hyperparameters

See `IJCAI2021-3457/args.yaml` or run `$ python3 IJCAI2021-3457/train.py --help`.

## Code Base
- https://github.com/rusty1s/pytorch_geometric/blob/master/examples 


