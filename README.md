# Finetuning T5 for Location Recognition

Timely information extraction can be life-saving, especially during disasters when knowing the exact location can assist in rescuing individuals. Developing automated systems for recognizing and geolocating toponyms is crucial to ensure faster and more effective responses.

### Data 

IDRISI-R is the largest-scale publicly-available Twitter Location Mention Recognition (LMR) dataset. The "R" refers to the recognition task. IDRISI-R contains 41 disaster events of different types (e.g., floods, earthquakes, fires, etc.) that occurred in a wide geographical areas across continents. You can find more about the data [here](https://github.com/rsuwaileh/IDRISI/tree/main/LMR).

### Model

Distaster tweets are cleaned and preprocessed by removing empty tweets, hyperlinks and other unnecessary strings that do not contribute to location extraction. Tweets are prefixed with "Extract locations :" to match with t5 model input format.

The fine-tuned model, specifically trained for location extraction from disaster-related tweets, is available in the fine-tuned-t5 directory. To obtain the fine-tuned model weights, you can clone the repository as shown below:

```
git clone https://github.com/bindusri0702/Extract_locations.git
```

Once cloned, navigate to the directory containing the model weights:

```
cd fine-tuned-t5
```

To load and utilize the fine-tuned model and tokenizer, execute the following Python code:

```python
from transformers import T5ForConditionalGeneration, T5Tokenizer

# Load the fine-tuned model and tokenizer
model = T5ForConditionalGeneration.from_pretrained('./fine-tuned-t5')
tokenizer = T5Tokenizer.from_pretrained('./fine-tuned-t5')

# Example usage:
# input_text = "Extract locations: Landslide in Wayanad had taken many lives."
# inputs = tokenizer(input_text, return_tensors="pt")
# output = model.generate(inputs.input_ids)
# decoded_output = tokenizer.decode(output[0], skip_special_tokens=True)
# print(decoded_output)

```
