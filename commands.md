# Auto-editor

cut nice  ?
```
# cut with spaces to breathe
auto-editor ".\2025-12-23 18-37-45.mp4" --margin 0.15sec --edit audio:threshold=-30dB

# cut fast pace
auto-editor ".\format tierlist_ALTERED.mp4" --margin 0.05sec --edit audio:threshold=-50dB
```

# FFMPEG

## Convert video from mp4 to mov to remove framerate issues

```bash
# Maxout quality
ffmpeg -i pt_ff_top8.mp4 -c:v prores_ks -profile:v 3 -vendor apl0 -bits_per_mb 8000 -c:a pcm_s16le pt_ff_top8.mov

# Lowest quality for edits
ffmpeg -i "part_001.mp4" -c:v prores_ks -profile:v 0 -c:a aac -b:a 192k "part_001.mov"

# Lowest quality No Audio (-an tag)
  ffmpeg -i "part_001.mp4" -c:v prores_ks -profile:v 0 -an "part_001.mov"
```



## Cut video in part of 5 minutes
```bash
ffmpeg -i pt_ff_top8.mp4 -c copy -map 0 -segment_time 300 -f segment F:\Videos\footage\mtg\pt_ff_top8\pt_ff_top8_%03d.mp4
```
