# snippets

## Minimal bash prompt
```sh 
export PS1='%* %1~ %B$%b '
```

## Transcode every .mov
```sh
for vid in *.mov; do ffmpeg -i "$vid" -c:v libx264 -c:a aac -b:v 2M "${vid%.*}.mp4"; done
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

## Generate Random String
```sh
openssl rand -hex 32
```

## Run command for every item in a set
```sh
#!/bin/bash
jobs=("bob" "alice" "eve")

for job in "${job[@]}"; do
  touch ./jobs/$job/$job.txt
done
```

## Make asymmetric keys
```sh
openssl genrsa -out private_key.pem 4096
openssl rsa -pubout -in private_key.pem -out public_key.pem
```

## Mux entire `.mp4` file to HLS
```sh
ffmpeg -i input.mp4 -f hls -hls_time 4 -hls_list_size 0 -hls_flags delete_segments ./out/video.m3u8
```

## Docker command reference
```sh
docker run container-name # create and run container
docker build -t image-name . # build image
docker create --name container-name image-name` # create container from image
docker run -it image-name sh # create container from image and shell into it
docker compose .
```
