# PORTFOLIO

**Spotify Cover Arts Analysis**

The aim of this project was:
* To investigate whether there are any patterns in the use of different colors in the cover arts of music releases depending on their genre;
* To determine the most common color scheme for the cover arts;
* To explore whether there is a correlation between the color used in the cover art and the musical characteristics of the release;
* To identify any trends in the use of colors over time and how they have changed.

All data was retrieved from Spotify Web API using Spotipy library: https://spotipy.readthedocs.io/en/2.22.1/

`parsing_dataset_+_ML_clustering.ipynb`
* Assumes you have a local folder to save the album covers (like '/content/tracks')
* play_lists contains a list of Spotify playlist IDs from which a dataframe is planned to be obtained

Process of color decomposition:
![My Image](https://github.com/jpegpunk/PORTFOLIO/blob/main/color_decomposition_example.png)
[An example of the cover art used in this picture: Divididos - La era de la boludez]
* Each image has a set of 8 unique colors, and with normal decomposition, I would end up with 8 x 85,605 = 684,840 colors, which is impractical. Therefore, I decided to convert each of the colors in the palette of each cover to one of 17 basic colors from the Lab Color Space
(https://en.wikipedia.org/wiki/CIELAB_color_space)

`correlation.ipynb`
* The results of the correlation analysis (using the point biserial correlation: https://en.wikipedia.org/wiki/Point-biserial_correlation_coefficient)

`cover_arts_analysis.ipynb`
* Results of the main cover analysis, clustering colors using K-Means, artist preference analysis, analysis of temporal trends in color usage.

`union_df.csv`
* Retrieved dataframe used for the whole analysis

Headers for union_df.csv are shown below:
Header | Description
---|---------
`id` | Spotify track ID
`title` | Track title
`all_artists` | Artist(s) of the track
`genres` | Genres in which the artist(s) work(s)
`cover` | URL to an image on the Spotify
`black` | Proportion of black color in the cover art palette
`gray` | Proportion of gray color in the cover palette
`silver` | Proportion of silver color in the cover palette
`white` | Proportion of white color in the cover palette
`maroon` | Proportion of maroon color in the cover palette
`red` | Proportion of red color in the cover palette
`orange` | Proportion of orange color in the cover palette
`yellow` | Proportion of yellow color in the cover palette
`olive` | Proportion of olive color in the cover palette
`green` | Proportion of green color in the cover palette
`lime` | Proportion of lime color in the cover palette
`teal` | Proportion of teal color in the cover palette
`cyan` | Proportion of cyan color in the cover palette
`navy` | Proportion of navy color in the cover palette
`blue` | Proportion of blue color in the cover palette
`purple` | Proportion of purple color in the cover palette
`pink` | Proportion of pink color in the cover palette
`popularity` | The popularity of the track. The value will be between 0 and 100, with 100 being the most popular
`release_date` | Release date
`danceability` | Describes how suitable a track is for dancing (0.0 is least danceable and 1.0 is most danceable)
`energy` | Perceptual measure of intensity and activity (from 0.0 to 1.0)
`key` | The key the track is in. Integers map to pitches using standard Pitch Class notation (https://en.wikipedia.org/wiki/Pitch_class)
`loudness` | The overall loudness of a track in decibels (dB)
`mode` | Mode indicates the modality (major or minor) of a track (major is represented by 1 and minor is 0)
`acousticness` | A confidence measure from 0.0 to 1.0 of whether the track is acoustic
`instrumentalness` | Predicts whether a track contains no vocals
`liveness` | Detects the presence of an audience in the recording
`valence` | A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track
`tempo` | The overall estimated tempo of a track in beats per minute (BPM)
`duration_ms` | The duration of the track in milliseconds
`time_signature` | The time signature ranges from 3 to 7 indicating time signatures of "3/4", to "7/4"
`artist_id` | Spotify artist(s) ID(s)
