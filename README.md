
This project uses Natural Language Processing (NLP) to analyze the emotional
mood of song lyrics. By using text preprocessing, a fine-tuned DistilRoBERTa
emotion classifier, and data visualization, the system transforms some lyrics
into structured emotional ideas.

Final product is the intellectual property of Stanford NLP Group.

1. Preprocessing
   - Converts lyrics to lowercase
   - Removes punctuation
   - Removes whitespace
 

2. NLP Classification
   - Uses Hugging Face DistilRoBERTa model trained for multi-emotion detection
   - Generates probability scores for emotions such as joy, sadness, anger, love, fear
   - Applies a threshold (default ≥ 0.25) to capture many dominant moods, if necessary
   - Falls back to single highest-scoring mood if no score crosses threshold

3. Batch Processing
   - Reads input from CSV file (song_lyrics.csv) with title, artist, lyrics
   - Processes lyrics in batches to go quicker and be more efficient
   - Outputs results with two new columns:
       * dominant_moods → list of strongest moods
       * mood_scores → dictionary of all emotion probabilities
   - Saves annotated dataset to song_lyrics_mood_analysis.csv

4. Visualizations
   - bar chart (mood_distribution.png)
       * Summarizes frequency of each dominant mood across the dataset
   - Per-song radar charts (mood_charts/*.png)
       * Shows full emotional moods and ideas of each song
       * One chart saved per track with all mood intensities plotted

