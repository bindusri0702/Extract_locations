# Finetuning T5 for Location Recognition

Timely information extraction can be life-saving, especially during disasters when knowing the exact location can assist in rescuing individuals. Developing automated systems for recognizing and geolocating toponyms is crucial to ensure faster and more effective responses.

### Data 

IDRISI-R is the largest-scale publicly-available Twitter Location Mention Recognition (LMR) dataset. The "R" refers to the recognition task. IDRISI-R contains 41 disaster events of different types (e.g., floods, earthquakes, fires, etc.) that occurred in a wide geographical areas across continents. You can find more about the data [here](https://github.com/rsuwaileh/IDRISI/tree/main/LMR).

### Model

Distaster tweets are cleaned and preprocessed by removing empty tweets, hyperlinks and other unnecessary strings that do not contribute to location extraction. Tweets are prefixed with "Extract locations :" to match with t5 model input format.
