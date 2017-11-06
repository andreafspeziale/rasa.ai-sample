## first path               <!-- name of the story - just for debugging -->
* _greet
  - utter_greet
* _goodbye               <!-- user utterance, in format _intent[entities] -->
  - utter_goodbye

## second path
* _greet
  - utter_greet
* _search_user_by_location
  - utter_search_user_by_location