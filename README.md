# Cross-Cultural Aesthetic Mapping in Music

Analyzing how mood and genre descriptors map to different acoustic profiles across cultural listening contexts — testing whether categories that music recommendation systems treat as universal are actually culturally particular.

## Motivation

Music recommendation systems rely on mood and genre categories ("nostalgic," "melancholic," "energetic") as if they mean the same thing everywhere. But what sounds "nostalgic" to a Japanese listener (city pop, 80s synth, certain enka styles) is systematically different from what sounds "nostalgic" to an American or Brazilian listener.

If these categories are culturally conditioned rather than universal, then recommendation systems trained without cultural awareness will systematically misserve cross-cultural listeners — someone whose taste spans Japanese city pop and Brazilian MPB won't be well served by a model that learned "nostalgic" from American listening data.

This project investigates:
- **Do mood descriptors correspond to different acoustic profiles across cultures?**
- **How large and systematic are the divergences?**
- **Does a mood classifier trained on one culture's data transfer to another?**

## Method

### Data Collection
- Use Spotify's public API (via `spotipy`) to search for playlists tagged with mood descriptors in multiple languages:
  - English: "nostalgic," "melancholic," "energetic," "chill," "upbeat"
  - Japanese: 懐かしい, 切ない, 元気, リラックス
  - Portuguese: nostálgico, melancólico, energético, relaxante
- Pull 20-30 playlists per mood per language
- For each playlist, retrieve track audio features (tempo, energy, valence, danceability, acousticness, instrumentalness) and artist genre tags

### Analysis
1. **Feature distribution comparison**: Compare distributions of audio features for same-mood playlists across cultures (violin plots, KS tests)
2. **Genre composition analysis**: Compare artist genre distributions across cultures for same-mood playlists
3. **Cross-cultural transfer test**: Train a simple mood classifier on one culture's data, test on others — measure accuracy drop as evidence that mood-feature mappings are culturally specific
4. **Qualitative case studies**: Deep dives into the most divergent mood categories with specific track examples

## Repository Structure

```
cross-cultural-music/
├── README.md
├── data/
│   ├── collection/        # Scripts for Spotify API data collection
│   └── playlists/         # Collected playlist and track data
├── analysis/
│   ├── feature_distributions.py
│   ├── genre_analysis.py
│   └── cross_cultural_classifier.py
├── figures/               # Visualization outputs
└── notes/
    └── observations.md    # Running observations and findings
```

## Requirements

```
spotipy
pandas
numpy
matplotlib
seaborn
scikit-learn
```

## Status

🟡 **In progress** — Setting up Spotify API access and data collection pipeline.

## Related Work

- Schedl et al. "Current Challenges and Visions in Music Recommender Systems Research." (Spotify Research)
- Spotify Research. "Generalized User Representations for Large-Scale Recommendations." 2025.
- Hong et al. (2026). "Deconstructing Taste: Toward a Human-Centered AI Framework for Modeling Consumer Aesthetic Perceptions."

## Contact

Weidi Li — weidili92@gmail.com
