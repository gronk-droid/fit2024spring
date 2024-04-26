### CSE4224: Project 2 Proposal

##### Grant Butler | gbutler2020@my.fit.edu

#### Project Goals

1. To use t-Stochastic Neighbors Embedding (_t_-SNE) to analyze Spotify tracks for similarities between genres.
2. To bring together different collections of songs based on the model, ultimately for use in averaging what characteristics of the sounds make them similar/unique.
3. For further study, to take this data and model and use it to make unique musical samples that could be used to approximate **_the_** sound of the grouped tracks.

#### Data Collection/Processing

In order to retrieve the data, Spotify's API will be used to find a track's audio features, and/or audio analysis. The Audio Features include information like "acousticness, danceability, or liveness," providing ways to have the tracks be grouped. The Audio Analysis provides detailed and timestamped information regarding the audio itself. In particular, the "timbre" of the track, which would indicate a detailed analysis of each tracks audio through a Fourier-transform to see the spectrograph, allowing for an analysis of the sound that makes the groupings of these tracks unique and interesting.This information will be taken from my own personal Spotify account's listening history.After retrieving the data, checking for any missing values in the tracks and handling those entries will thin out the total set. After that, since the Spotify API's data seems to be quite clean and it should be good to start working with. Starting by reducing the number of dimensions the data has should help to expedite the training of the model. By applying PCA beforehand, it will then be easier to use _t_-SNE on it, and visualize the data afterwards.

#### Methods

Using `sklearn`'s PCA and TSNE modules, the data will be put into an `np.array`, scaled using the `StandardScaler`, and then put into PCA. This will reduce the dimensionality of the data to limit the cost of using _t_-SNE. After that, the data will be piped into TSNE, and the data will be visualized. If further time after that is found, using another method like MDS and trying to find other ways of relating the tracks to each other would be explored.