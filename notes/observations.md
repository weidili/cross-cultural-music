# Running Observations

## Initial Hypotheses

### "Nostalgic" will diverge most
- Japanese nostalgia in music often maps to city pop, 80s synth-pop, certain enka styles
- American nostalgia often maps to classic rock, Motown, 70s/80s pop
- Brazilian nostalgia often maps to MPB, bossa nova, early tropicália
- Prediction: tempo and instrumentation distributions will differ significantly

### "Melancholic" may also diverge
- Japanese: 切ない (setsunai) is bittersweet/tender sadness — not the same as Western "melancholic"
- The concept doesn't map cleanly onto English emotion categories
- Brazilian: saudade is its own thing — longing/nostalgia/melancholy blended

### "Energetic" might converge more
- High-energy music may share more universal acoustic features (high tempo, high energy)
- But genre expression of energy could still differ (J-pop vs. American hip-hop vs. Brazilian funk)

---

## Data Collection Notes

*Updating as collection progresses*

### Spotify API setup
- Using spotipy library
- Need developer account at developer.spotify.com
- Search endpoint for playlists by mood keyword in each language
- Audio features endpoint for track-level features

### Search terms by language

| Mood | English | Japanese | Portuguese |
|------|---------|----------|------------|
| Nostalgic | nostalgic, nostalgia | 懐かしい, ナツカシイ | nostálgico, nostalgia |
| Melancholic | melancholic, melancholy, sad | 切ない, 悲しい | melancólico, saudade |
| Energetic | energetic, hype, pump up | 元気, テンション上がる | energético, animado |
| Chill | chill, relaxing, calm | リラックス, まったり | relaxante, calmo |

---

## Questions to Explore

- Are the divergences in audio features or in genre composition or both?
- Does within-culture variance exceed between-culture variance for any mood? (Would weaken the claim)
- Can I find users/playlists that span multiple cultures? What do their mood playlists look like?
- Is there a "universal core" to any mood that holds across cultures, with cultural variation on top?
