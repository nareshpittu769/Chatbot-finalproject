

## Installation

### Create an environment
Whatever you prefer (e.g. `conda` or `venv`)
```console
mkdir myproject
$ cd myproject
$ python3 -m venv venv
```

### Activate it
```console
venv\Scripts\activate
```
### Install PyTorch and dependencies

For Installation of PyTorch see [official website](https://pytorch.org/).

You also need `nltk`:
 ```console
pip install nltk
 ```

If you get an error during the first run, you also need to install `nltk.tokenize.punkt`:
Run this once in your terminal:
 ```console
$ python
>>> import nltk
>>> nltk.download('punkt')
```

## Usage
Run
```terminal
python train.py
```
This will dump `data.pth` file. And then run
```terminal
python chat.py
```
## Customize
Have a look at [intents.json](intents.json). You can customize it according to your own use case. Just define a new `tag`, possible `patterns`, and possible `responses` for the chat bot. You have to re-run the training whenever this file is modified.
```
{
  "intents": [
    {
      "tag": "greeting",
      "patterns": [
        "Hi",
        "Hey",
        "How are you",
        "Is anyone there?",
        "Hello",
        "Good day"
      ],
      "responses": ["Hello,\nThanks for visiting CETA. How may I help you?"]
    },
    {
      "tag": "goodbye",
      "patterns": ["Bye", "See you later", "Goodbye"],
      "responses": [
        "See you later, thanks for visiting",
        "Have a nice day",
        "Bye! Come back again soon."
      ]
    },
    {
      "tag": "thanks",
      "patterns": ["Thanks", "Thank you", "That's helpful", "Thank's a lot!"],
      "responses": ["Happy to help!", "Any time!", "My pleasure"]
    },
    {
      "tag": "events",
      "patterns": [
        "How many events are there?",
        "What kinds of events are there?",
        "Does event takes place?",
        "can you help me with the events?",
        "I would like to know about the ongoing events?",
        "Any events are there?",
        "About events?",
        "Events?"
      ],
      "responses": [
        "Yes, there are two events are happening right now.\nTechnical Events\nNon-technical Events"
      ]
    },
    {
      "tag": "technical",
      "patterns": [
        "What are the technical events?",
        "What do we have in technical events?",
        "How many technical events are there?",
        "I would like to know about the technical events?",
        "I want to know about the technical events!",
        "Technical events!",
        "Technical"
      ],
      "responses": [
        "Thank you for choosing technical events,\n we have coding,group discussions,seminars and jam."
      ]
    },
    {
      "tag": "non-technical",
      "patterns": [
        "What are the non-technical events?",
        "How many contests are there in non-technica?",
        "I want to know about the non-technical events?",
        "I would like to know about the non-technical events",
        "Non-technical events?",
        "Non-technical"
      ],
      "responses": ["Glad!!!\n we have sports,dance,music and standup."]
    },
    {
      "tag": "date",
      "patterns": [
        "When is the last date for registrations?",
        "Date for registrations?",
        "When are registrations can be done?",
        "Deadline for registrations?",
        "Deadline date?",
        "Date?"
      ],
      "responses": ["The last date to register is 6TH FEB,2023."]
    }
  ]
}
```
