## RecSys2024_Challenge

The RecSys 2024 Challenge: https://www.recsyschallenge.com/2024/

The Ekstra Bladet RecSys Challenge aims to predict which article a user will click on from a list of articles that were seen during a specific impression. Utilizing the user's click history, session details (like time and device used), and personal metadata (including gender and age), along with a list of candidate news articles listed in an impression log, the challenge's objective is to rank the candidate articles based on the user's personal preferences. 

We introduce a method that utilizes Graph Neural Networks (GNNs) to model user sessions as graphs for predicting user click behavior on news articles. By transforming user interactions into graph structures, our approach captures both direct and indirect relationships between articles, offering a more comprehensive understanding of user preferences compared to traditional methods.

Our proposed method represents each user session as a directed graph, where nodes correspond to articles a user interacts with and edges capture sequential transitions (including temporal proximity and interaction frequency). Each node is enriched with comprehensive article-level features, such as metadata (publication date, category, author) and embeddings derived from pre-trained language models (e.g., BERT or GloVe).

1. Download the datasets at: https://recsys.eb.dk/#dataset

2. Unzip the data files to the following

    ```bash
    cd ~/RecSys2024_CTR_Challenge/data/Ebnerd/
    find -L .

    .
    ./train
    ./train/history.parquet
    ./train/articles.parquet
    ./train/behaviors.parquet
    ./validation
    ./validation/history.parquet
    ./validation/behaviors.parquet
    ./test
    ./test/history.parquet
    ./test/articles.parquet
    ./test/behaviors.parquet
    ./image_embeddings.parquet
    ./contrastive_vector.parquet
    ./prepare_data_v1.py
    ```

3. Convert the data to csv format

    ```bash
    cd ~/RecSys2024_CTR_Challenge/data/Ebnerd/
    python prepare_data_v1.py
    ```




    ```

# Dataset

Directories:
+ Ebnerd: raw data
+ Ebnerd_large_x1: preprocessed csv data
+ ebnerd_large_x1_xxxxxxxx: preprocessed npz data
