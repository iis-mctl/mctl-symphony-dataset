# **Detailed Dataset Information**

## **Dataset Structure**

This section presents the hierarchical structure of the dataset, outlining the organization of files and directories for each piece:

```css
<piece_name>
    ├── sheet.pdf
    ├── sheet.xml
    └── Annotations
        ├── temporal_attributes
        │   └── measure_num.txt
        │   └── time_signature.csv
        │   └── downbeat.csv       
        ├── form
        │   ├── harmony.csv
        │   ├── form_analysis.csv
        │   ├── cadence.csv
        │   └── form_annotation.pdf
        ├── layers
        │   ├── layers.pdf
        │   └── <instrument>.csv
        ├── note
        │   └── <instrument>.csv
        └── note_played
            └── note_played.csv

```

## Harmony Details

### Columns and Descriptions

| Column       | Description                                      | Example 1   | Example 2  |
|--------------|--------------------------------------------------|-------------|------------|
| onset        | In crotchet beats                                | 12          | 168        |
| offset       | In crotchet beats                                | 16          | 168.5      |
| key          | Tonality <br> `R/r` for Major/minor <br> `+/-` for sharp/flat | e           | B          |
| degree       | 1, 2, 3, 4, 5, 6, 7 <br> `+/-` before number for sharp/flat <br> `/` for secondary chord  | 7/5         | 5/3        |
| quality      | major triad (M) <br> minor triad (m) <br> diminished triad (d) <br> major 7th (M7) <br> minor 7th (m7) <br> dominant 7th (D7) <br> diminished 7th (d7) <br> half-diminished 7th (h7) <br> augmented (a) <br> augmented 6th (a6) | d7 | M |
| inversion    | 0, 1, 2, 3                                       | 1           | 0          |
| roman number | Roman numeral notation                           | vii-65/V    | V/III      |

### Roman Numeral Notation

| Symbol         | Description                                  |
|----------------|----------------------------------------------|
| Upper case Roman numeral | Major triad                       |
| Lower case Roman numeral | Minor triad                       |
| Upper case with '+'      | Augmented triad                   |
| Lower case with '-'      | Diminished triad                  |
| Upper case with '^7'     | Major 7th chord                   |
| Lower case with '7'      | Minor 7th chord                   |
| Lower case with '-7'     | Diminished 7th chord              |
| Lower case with '=7'     | Half diminished 7th chord         |
| Lower case with '^7'     | Minor major 7th chord             |
| Upper case with '+7'     | Augmented dominant 7th chord      |
| 6                        | Triad (1st inversion)             |
| 64                       | Triad (2nd inversion)             |
| 7                        | 7th chord (root position)         |
| 65                       | 7th chord (1st inversion)         |
| 43                       | 7th chord (2nd inversion)         |
| 42                       | 7th chord (3rd inversion)         |
| N6                       | Neapolitan chord                  |
| It+6                     | Italian sixth                     |
| Fr+6                     | French sixth                      |
| Gr+6                     | German sixth                      |