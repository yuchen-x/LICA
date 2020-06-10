# Learning Implicit Credit Assignment for Multi-Agent Actor-Critic (LICA)

This repository hosts the implementation of **LICA: Learning Implicit Credit Assignment for Multi-Agent Actor-Critic**. The implementation in written in PyTorch and is based on the [PyMARL](https://github.com/oxwhirl/pymarl) framework with [SMAC](https://github.com/oxwhirl/smac) as the environment.

## Setup

Set up the working environment:

```shell
pip3 install -r requirements.txt
```

Set up the StarCraftII game core

```shell
bash install_sc2.sh
```

## Training

To train `LICA` on the `5m_vs_6m` scenario,

```shell
python3 src/main.py --config=lica --env-config=sc2 with env_args.map_name=5m_vs_6m
```

Change the `map_name` accordingly for other environments. All results will be saved in the `results` folder.


## Evaluation

### Saving models
Same as Pymarl, set `save_model` to `True` in `src/config/default.yaml` will save the learnt model during training (saved in `result/` directory be default). The frequency of saving models can be adjusted using `save_model_interval` configuration.

### Loading models
The learnt model can be loaded by adjusting the `checkpoint_path` parameter in `src/config/default.yaml`. For instance, to load model under path `result/model/[timesteps]/agent.th`, set `checkpoint_path` to `result/model/[timesteps]`.

### Saving Starcraft II Replay
The learnt model loaded from `checkpoint_path` can be evluated by setting `evaluate` to `True` `src/config/default.yaml`. To save the Starcraft II Replay, please make sure configure `save_replay` to `True`, and use the episode runner.

Check out [Pymarl documentation](https://github.com/oxwhirl/pymarl) for more information.


## Visualization
The videos of two of the best battles performed by LICA agents (red) are available under path `/visualization`. The GIF previews are shown below:

### 5m_vs_6m
<img src="gifs/5m_vs_6m.gif" width="100%">


### MMM2
<img src="gifs/MMM2.gif" width="100%">


## See Also

See [SMAC](https://github.com/oxwhirl/smac) and [PyMARL](https://github.com/oxwhirl/pymarl) for additional instructions.
