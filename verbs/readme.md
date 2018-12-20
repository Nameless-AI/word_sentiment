## About
The json files contain models describing sentimental effects for verbs. The general idea is that verbs have location or state effects on nouns depending on their nature -- people, animals, places and things.
The word models are split/organized based on the first character of the verb for easy editing.

## Contributing

To contribute, simply open any of the json files and append to it following the json structure. 

To find verbs to work on, a good starting point is here: https://github.com/Drulac/English-Verbs-Conjugates/blob/master/infinitiv-verbs-list.json

OR here: https://github.com/datmt/English-Verbs/blob/master/verbsList

### JSON STRUCTURE

    {
      "verb_word": {
        "effects": [
          {
            wcat: integer,//1=Person,2=Place,4=Animal,8=Thing,
            is_subject: boolean,
            modifies: integer,//1=state,2=location
            expected_state: string,//nullable qualifier/location (adjective), direction or "o_l = object location or "s_l" = subject location
            final_state: string,//nullable qualifier/location (adjective), o_l = object location, s_l = subject location
            sentimental_effect: integer,//3=object sentiment,2=subject sentiment,1=positive,0=neutral,-1=negative,-2=negated subject sentiment,-3=negated object sentiment
          },
          ...
        ]
      }
    }

*Example*

    {
      "come": {
        "effects": [{
          "wcat": 1,
          "is_subject": true,
          "modifies": 2,
          "expected_state": "s_l",
          "final_state": "o_l",
          "effect": 3
        }]
      }
    }