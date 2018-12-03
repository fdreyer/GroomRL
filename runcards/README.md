Runcard setup
=============

Parameters are defined through a runcard which is stored in json format.

It is made of a dictionary with several entries

## groomer_env
The groomer_env entry is itself a dictionary containing all the
environment parameters for the groomer.
- fn: the data set used for the fit
- mass: the target mass
- nev: number of events to load
- width: width parameter used in the reward
- reward: functional form of the mass reward (cauchy, gaussian, exponential, inverse)
- SD_groom: form of the groomed SD reward (exp_add, exp_mult)
- SD_keep: form of the ungroomed SD reward (exp_add, exp_mult)
- alpha1: parameter for groomed SD reward
- alpha2: parameter for kept SD reward
- SDnorm: normalisation factor for SD reward
- lnzRef1: parameter for groomed SD reward
- lnzRef2: parameter for kept SD reward
- state_dim: dimensionality of the observable state
- fn_bkg: data set used for the background (for GroomEnvDual)
- width_bkg: parameter used for background reward
- dual_groomer_env: use GroomEnvDual instead of GroomEnv (true or false)

## groomer_agent
The groomer_agent contains all the parameters for the DQN and NN
- learning_rate: learning rate for Adam
- policy: policy used (boltzmann or epsgreedyq)
- enable_dueling_network: enable dueling network option (true or false)
- enable_double_dqn: enable double dqn option (true or false)
- nstep: number of steps in the fit
- architecture: model architecture (Dense, LSTM)
- dropout: value for dropout layer (ignored if 0)
- nb_units: number of units in NN
- nb_layers: number of layers for Dense architecture

## cluster
The parameters for cluster runs
- enable: enable cluster mode (true or false)
- url: url for MongoTrials
- exp_key: exp_key parameter

## test
Contains information about the test data
- fn: test file for diagnostic plots
- fn_bkg: test file of background events for diagnostic plots