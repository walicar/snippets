# snippets

## Minimal bash prompt
```sh 
export PS1='%* %1~ %B$%b '
```

## Transcode every .mov
```sh
for vid in *.mov; do ffmpeg -i "$vid" -c:v libx264 -c:a aac -b:v 2M "${i%.*}.mp4"; done
```

## List every .cc file
```sh 
find ./ -name "*.cc"`
```

## For every file, make every underscore a hyphen
```sh
for file in *_*; do mv "$file" "${file//_/-}"; done
```

## Show context from grep
```sh
ffmepg -h | grep aspect -B 5 -A 5
```

## Run command for every item in a set
```sh
#!/bin/bash
jobs=("bob" "alice" "eve")

for job in "${job[@]}"; do
  touch ./jobs/$job/$job.txt
done
```
