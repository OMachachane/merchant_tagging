# merchant_tagging

2 NER models for Tagging

- The first one is a general NER model from spacy library
- The second one is an customised NER model with merchant names
- The length of the original dataset is 2280287 (includingg unknown merchants)
- The models were implemented the dataset with known merchants - with 1133623 length

New columns:
- Columns "txn_desc1" and "txn_desc2" were concatenated, resulting in the "CONCAT_COLS" column
- Column "merchant_name" was copied from the original dataset, resulting in the "AFS_MECHANT_NAMES"
- Column named "NER_RAW_MODEL" was created for the general ner model implementation
- Column "PREDICTIONS" was created for the NER model with merchant names
- Column "CHECK" was created to inspect the "PREDICTIONS" results (True / False)
- Column "SIMILARITY" was created to score the levels of similarity between "PREDICTIONS" and "AFS_MECHANT_NAMES"

Strategy:
- Find all the known organisations in the original dataset - 536 different organisations (variable "dist_list")
- Add all the organisations in the NER model using entity rules technique to add them as rules/patterns to the model
- Implement the model in all the entries and find organisations/"ORG" - function "find_org"
- Avoid some useless organisations or strings from "junk" list to improve accuracy levels
- Tag all the entries with the predicted values in the "PREDICTIONS" column
- Analyse similarity levels using fuzzywuzzy library to compare and score the results (from 0 to 100) - function "check_names"
- Return True if merchant name is in the result and False if it is not - in the "CHECK" column
 

Accuracy: 30%
Dataset length:1133623
