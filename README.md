# Spotify

<!-- Salut les gars,<br/>
Pour le projet Spotify je vous propose des pistes à approfondir pour qu'on puisse avancer alors si vous avez des suggestions, je suis preneur. Concerant l'organisation du projet, je vois 4 parties:
<br/><br/><br/>

- [PARTIE 1 -> 1 personne] Data retrieval + data preprocessing: 

Récupération de la donnée (via [Kaggle](https://www.kaggle.com/code/stpeteishii/spotify-popularity-predict-visualize-importance/data) ou via une API, comme [Spotipy](https://spotipy.readthedocs.io/en/2.21.0/#) ) et nettoyage de la donnée en fonction de nos besoins. On a déjà les données via Kaggle donc on pourrait envisager de récupérer de la data par API.
<br/><br/>

- [PARTIE 2 -> 1-2 personnes] Exploratory Data Analysis (EDA) + clustering: 

Analyse du dataset de long en large (analyse des NaN, lignes dupliquées, données incohérentes, ..) pour une compréhension parfaite des relations entre features (visualisation simple avec la librairie [Plotly](https://plotly.com/python/). L'idée serait de comprendre la répartition/distribution de la data pour certaines features (voir ci-dessous la description des features) et d'établir potentiellement des relations feature-feature. On pourrait également faire du **clustering** ([K-NN, K-Means](https://becominghuman.ai/comprehending-k-means-and-knn-algorithms-c791be90883d)) pour comprendre les différents groupes de tracks existants ou encore faire de **l'analyse de sentiments** (avec [TextBloB](https://towardsdatascience.com/my-absolute-go-to-for-sentiment-analysis-textblob-3ac3a11d524)) sur le track_name pour explorer le lien popularity = f(track_name).
<br/><br/>

- [PARTIE 3 -> 1-2 personnes] Popularity prediction: 

Analyse des *features importances* liées au calcul du score de popularity et prédiction du score de popularité ([LGBM](https://lightgbm.readthedocs.io/en/v3.3.2/), [XGBoost](https://xgboost.readthedocs.io/en/stable/), ..). L'idée serait de nettoyer le dataset puis de le split l'entrainement du modèle et de faire des comparaisons d'efficacité entre algorithmes.
<br/><br/>

- [PARTIE 4 -> 1-2 personnes] Recommender System (content based filtering): 

Création d'un système de recommandation s'appuyant sur le contenu (content based filtering). L'idée serait de faire du **[One Hot Encoding](https://machinelearningmastery.com/how-to-one-hot-encode-sequence-data-in-python/)** pour recommander des tracks similaires (par **[cosine similarity](https://towardsdatascience.com/hands-on-content-based-recommender-system-using-python-1d643bf314e4)** par exemple). Il existe pleins de façons de faire !
<br/><br/><br/>

Les features pourraient se répartir en 3 groupes:
1. Metadata (track_id, artists, album_name, track_genre, popularity)
2. Audio (MOOD: danceability, valence, energy, tempo) + (PROPERTIES: loudness, speechiness, instrumentalness) + (CONTEXT: duration_ms, liveness, acousticness) + (METADATA: explicit, key, mode, time_signature)
3. Text (track_name)


 -->

### 

## About Dataset
#### Content
This is a dataset of Spotify tracks over a range of 125 different genres. Each track has some audio features associated with it. The data is in CSV format which is tabular and can be loaded quickly.

#### Usage
The dataset can be used for:
- Building a Recommendation System based on some user input or preference
- Classification purposes based on audio features and available genres
- Any other application that you can think of. Feel free to discuss!

#### Column Description
- track_id: The Spotify ID for the track
- artists: The artists' names who performed the track. If there is more than one artist, they are separated by a ;
- album_name: The album name in which the track appears
- track_name: Name of the track
- popularity: The popularity of a track is a value between 0 and 100, with 100 being the most popular. The popularity is calculated by algorithm and is based, in the most part, on the total number of plays the track has had and how recent those plays are. Generally speaking, songs that are being played a lot now will have a higher popularity than songs that were played a lot in the past. Duplicate tracks (e.g. the same track from a single and an album) are rated independently. Artist and album popularity is derived mathematically from track popularity.
- duration_ms: The track length in milliseconds
- explicit: Whether or not the track has explicit lyrics (true = yes it does; false = no it does not OR unknown)
- danceability: Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall - regularity. A value of 0.0 is least danceable and 1.0 is most danceable
- energy: Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale
- key: The key the track is in. Integers map to pitches using standard Pitch Class notation. E.g. 0 = C, 1 = C♯/D♭, 2 = D, and so on. If no key was detected, the value is -1
- loudness: The overall loudness of a track in decibels (dB)
- mode: Mode indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0
- speechiness: Speechiness detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words. Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks
- acousticness: A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic
instrumentalness: Predicts whether a track contains no vocals. "Ooh" and "aah" sounds are treated as instrumental in this context. Rap or spoken word tracks are clearly "vocal". The closer the instrumentalness value is to 1.0, the greater likelihood the track contains no vocal content
- liveness: Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live. A value above 0.8 provides strong likelihood that the track is live
- valence: A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry)
- tempo: The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration
- time_signature: An estimated time signature. The time signature (meter) is a notational convention to specify how many beats are in each bar (or measure). The time signature ranges from 3 to 7 indicating time signatures of 3/4, to 7/4.
- track_genre: The genre in which the track belongs
