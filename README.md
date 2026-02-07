# Sample Output 
https://github.com/user-attachments/assets/9ea52d15-9da6-4257-9369-9888f18f572d
# Dictionary Parser for Anki

This project is a dictionary parser designed to convert non-importable dictionary data into Anki-importable formats

The core issue:
- Anki does **not** allow importing folders as decks
- Anki only supports structured text imports:
  - `.csv`
  - `.tsv`
  - `.txt`
- The source dictionary data existed as **HTML files**, not plain text
- Direct import into Anki was therefore impossible

## Why Parsing Was Necessary
- Dictionary data contained HTML files rather than plaintext
- Dictionary entries contain nested tags for meaning, pronunciation, and components
- Stripping HTML tags destroys structure and relationships
- Proper extraction requires understanding how the information is stored in HTML

## Approach
- Parse HTML dictionary files to extract structured entries
- Use regular expressions to:
  - Identify word occurrences
  - Count how often a word appears inside other words
- Apply frequency analysis to prioritize anagrams

The parser is designed around learning efficiency:
- Words that appear frequently inside other words provide higher learning return
- Learning these components first:
  - Improves pattern recognition
  - Accelerates vocabulary acquisition
- This mirrors learning roots or phonetic components before full words

## Anki Field Design

Each dictionary entry is split into three independent Anki fields:
- **Semantics**
  - Meaning, definition, usage
- **Sound Components**
  - Pronunciation-related elements
- **Total Frequency**
  - Combined appearance count across semantic and phonetic contexts

## Output Format

- Final output is exported as:
  - CSV
- Each row represents a single dictionary unit
- Each column maps directly to an Anki field

# Demo
https://github.com/user-attachments/assets/b3dd0c70-5664-4972-895e-08ed0af4ecbd


--- 
