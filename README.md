# S3: A symbolic music dataset for computational music analysis of symphonies

Symbolic Symphony Set (S3), a high-quality, cross-period dataset comprising four symphonies, 16 movements by Mozart, Beethoven, Dvoˇrák, and Tchaikovsky, containing information on temporal attributes, note events, musical form, and orchestral texture. 

The dataset includes 285,387 notes, 532 phrases, and 7,290 chords. We consider the following bar-wise (attributes shared across all instrument tracks) and track-wise(specific for each individual instrument track) annotations of classical and romantic symphonies. Our dataset can be utilized for orchestral texture classification, advancing music modeling and generation, and offering new insights into compositional studies and analysis.

More information can be found here: 
[Z.-S. Lin*, Y.-C. Kuo*, T.-Y. Hung, W.-Y. Lin, Y.-H. Chu, T.-K. Wang, J.-H. Huang, C. Chang, C. Julio, G. Hsieh, and L. Su (2024), “S3: A Symbolic Music Dataset for Computational Music Analysis of Symphonies”, in Extended Abstracts for the Late Breaking Demo Session of the 25th Int. Society for Music Information Retrieval Conf., 14th November 2024, San Francisco, United States.](<https://ismir2024program.ismir.net/lbd_463.html>)


## **Overview**

- Digital scores: musicXML, PDF files in `<piece_name>`
- Annotations: .csv files in `<piece_name>/Annotations`
- Each piece contains annotations in four categories:
    - Note Events
    - Temporal Attributes
    - Musical Form
    - Orchestral Layers

## Corpus and Piece Names

We utilize four symphonies with entire movements by Mozart, Beethoven, Tchaikovsky, and Dvorak, spanning from the classical to the romantic period. Below are the symphonies, their segments, ranges, and abbreviations:

| Symphony | Segment # | Range | <piece_name> |
| --- | --- | --- | --- |
| Mozart Symphony No. 41 in C major | 4 | full | `mo1`, `mo2`, `mo3`, `mo4` |
| Beethoven Symphony No. 9 in D minor | 4 | full | `be1`, `be2`, `be3`, `be4` |
| Tchaikovsky Symphony No. 6 in B minor | 4 | full | `tc1`, `tc2`, `tc3`, `tc4` |
| Dvorak Symphony No. 9 in E minor | 4 | full | `dv1`, `dv2`, `dv3`, `dv4` |


## Annotations
### **1. Note Events**

Detailed note-level data for each instrument:

| Column           | Description                                               |
|------------------|-----------------------------------------------------------|
| onset            | The onset (measured in beats) of each note.               |
| offset           | The offset (measured in beats) of each note.              |
| midi number      | MIDI note number.                                         |
| duration         | Duration in crotchet beats.                               |
| staff            | Integers from zero for the top staff.                     |
| measure          | `-1` for incomplete measure.                                |
| beat in measure  | Position in crotchet beats, resetting to `0` at each measure.|
| instrument       | Name of the instrument in the orchestra.                  |


### **2. Temporal Attributes**

This section outlines the dataset's temporal components.

#### 2.1. Measure Number
Calculated measure numbers for each piece.

#### 2.2. Time Signature
Lists onset times, measure numbers, and their corresponding time signatures, indicating where changes occur to reflect structural shifts.

| Column           | Description                                               |
|------------------|-----------------------------------------------------------|
| onset            | The onset (measured in beats) of each note.               |
| measure          | `-1` for incomplete measure.             |
| time_signature_quarter_length | Number of quarter notes per complete measure. |                                      
| time_signature_numerator  | Numerator of the time signature, specifying beats per measure.|
| time_signature_denominator | Denominator of the time signature, indicating the note value for one beat.|

#### 2.3. Downbeat
Identifies the first beat of each measure.
              

### **3. Musical Form**

Includes harmony, form analysis, cadences, and form annotations.

#### 3.1. Harmony
Refer to [Harmony Details](https://github.com/kyuchia/mctl-symphony-dataset/tree/main/mctl_symphony_dataset#harmony-details) for detailed descriptions and examples.

| Column       | Description                                      | 
|--------------|--------------------------------------------------|
| onset        | In crotchet beats                                | 
| offset       | In crotchet beats                                | 
| key          | Tonality <br> `R/r` for Major/minor <br> `+/-` for `sharp/flat` |
| degree       | 1, 2, 3, 4, 5, 6, 7 <br> `+/-` before number for `sharp/flat` <br> `/` for secondary chord  |
| quality      | major triad (M) <br> minor triad (m) <br> diminished triad (d) <br> major 7th (M7) <br> minor 7th (m7) <br> dominant 7th (D7) <br> diminished 7th (d7) <br> half-diminished 7th (h7) <br> augmented (a) <br> augmented 6th (a6)|
| inversion    | 0, 1, 2, 3                                       | 
| roman number | Roman numeral notation                           | 



#### 3.2. Cadence

| Column        | Description                                                                     |
|---------------|---------------------------------------------------------------------------------|
| onset         | The onset (measured in beats) of each cadence.                                  |
| resolve time  | The duration from the first chord's onset to the last chord's onset in the cadence segment.|
| offset        | The offset (measured in beats) of each cadence.                                 |
| cadence type  | AC (Authentic Cadence), HC (Half Cadence), PC (Plagal Cadence), DC (Deceptive Cadence). |

#### 3.3. Form Analysis

| Column        | Description                                      |
|---------------|--------------------------------------------------|
| phrase onset  | The onset (measured in beats) of each phrase.    |
| phrase offset | The offset (measured in beats) of each phrase.   |
| theme         | A complete musical idea formed by multiple phrases, often including one or more cadences.|
| section       | A major part of a piece, consisting of multiple themes.|


### **4. Orchestral Layers**

Layer information for all instruments in symphonies.

| Column     | Description                                      |
|------------|--------------------------------------------------|
| onset      | The onset (measured in beats) of each layer.     |
| offset     | The offset (measured in beats) of each layer.    |
| role       | The function of the layer in the orchestral texture. |
| instrument | Name of the instrument in the orchestra.         |

### Orchestral Texture

| Role                     | Syntax          |
|--------------------------|----------------------|
| **Melody**               | `mel`                  |
| **Rhythmic accompaniment** | `rhythm`            |
| **Harmonic accompaniment** | `harm`              |
| **Mixed**                | `rhythm + harm`, `rhythm + mel`, `mel + harm`, `mel + rhythm + harm`|


## **Supplementary Material**
### **Note Played**

The columns represent the amount of notes played by each instrument in one movement.

| Column         | Description                                                |
|----------------|------------------------------------------------------------|
| n note played  | The number of notes played by each instrument in one movement. |
| instrument     | Name of the instrument in the orchestra.                   |

