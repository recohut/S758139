# DRGR: Deep Reinforcement learning based Group Recommender system

A course project for Georgia
Tech [CSE 6240 Web Search and Text Mining](https://www.cc.gatech.edu/~srijan/teaching/cse6240/spring2021/) Spring 2021.

## Dataset

The original MovieLens dataset can be downloaded from [MovieLens](https://grouplens.org/datasets/movielens/), and the
one we use is [MovieLens 1M Dataset](https://files.grouplens.org/datasets/movielens/ml-1m.zip). You can generate the
group data `MovieLens-Rand` by using `data/MovieLens-1M.zip` and `drgr/generator.py`. (See "Run the DRGR".)

The `data/MovieLens-Rand` directory should include the following files:

movies.dat:

* Movie information file from MovieLens-1M.

users.dat:

* User information file from MovieLens-1M.

groupMember.dat:

* File including group members.
* Each line is a group instance: groupID userID1,userID2,...

group(user)RatingTrain.dat:

* Train file.
* Each line is a training instance: groupID(userID) itemID rating timestamp

group(user)RatingVal(Test).dat:

* group (user) validation (test) file (positive instances).
* Each line is a validation (test) instance: groupID(userID) itemID rating timestamp

group(user)RatingVal(Test)Negative.dat:

* group (user) validation (test) file (negative instances).
* Each line corresponds to the line of group(user)RatingVal(Test).dat, containing 100 negative samples.
* Each line is in the format: (groupID(userID),itemID) negativeItemID1 negativeItemID2 ...

## Run the DRGR

Change to the code directory (if not in):

```
cd drgr
```

Generate the group data from the MovieLens-1M dataset (`data/MovieLens-1M.zip`):

```
python generator.py
```

Run the DRGR:

```
python main.py
```

## Parameters

We put all parameters in `config.py`.

## Tree
```
.
├── [5.6M]  images
│   ├── [5.5M]  deps.png
│   ├── [ 30K]  group_recommender_actorcritic_1.svg
│   ├── [ 10K]  group_recommender_actorcritic_2.svg
│   ├── [8.1K]  group_recommender_actorcritic_3.svg
│   ├── [ 12K]  group_recommender_actorcritic_4.svg
│   ├── [ 14K]  group_recommender_actorcritic_5.svg
│   ├── [ 13K]  group_recommender_actorcritic_6.svg
│   ├── [ 12K]  group_recommender_actorcritic_7.svg
│   ├── [ 21K]  group_recommender_actorcritic_8.svg
│   └── [5.9K]  S758139 | RL-based Group Recommender.svg
├── [150K]  nbs
│   └── [146K]  T381683_Group_Recommendations_with_Actor_critic_RL_Agent_in_MDP_Environment_on_ML_1m_Dataset.ipynb
├── [2.2K]  README.md
└── [ 52K]  src
    ├── [8.7K]  agent.py
    ├── [2.1K]  config.py
    ├── [ 10K]  data.py
    ├── [4.0K]  env.py
    ├── [2.6K]  eval.py
    ├── [ 13K]  generator.py
    ├── [2.3K]  main.py
    ├── [3.3K]  model.py
    └── [1.9K]  utils.py

 5.8M used in 3 directories, 21 files
```

## References

During the code implementation, we reference the following repositories and articles:

1. https://arxiv.org/abs/2106.06900)
2. AGREE: https://github.com/LianHaiMiao/Attentive-Group-Recommendation
3. LIRD: https://github.com/egipcy/LIRD
4. Recsys-RL: https://github.com/shashist/recsys-rl
5. GroupIM: https://github.com/CrowdDynamicsLab/GroupIM
6. Deep Deterministic Policy Gradients Explained: https://towardsdatascience.com/deep-deterministic-policy-gradients-explained-2d94655a9b7b