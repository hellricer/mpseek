# mpseek

Conditional search queries for Music Player Daemon (MPD).

## Usage

`$ mpseek '[condition] [keywords...]'`

## Examples:

```sh

 $ mpseek jazz

 $ mpseek '"michael jackson" album!=thriller'

 $ mpseek "genre=mpb|latin|soca brazil"

 $ mpseek 'genre="hip hop" && date>1990'

 $ mpseek "( genre=funk || album=funk ) && file=flac$"
```

## Dependencies

 - `bash`
 - `awk`
 - `xargs`
 - `mpc`

## Simple interactive prompt with history

```sh

#!/usr/bin/env bash

while true; do
    clear
    query=""
    read -p '> ' -e query
    if (( ${#query} )); then
        history -s "$query"
        mpc clear >&-
        mpseek "$query" | mpc add
    fi
done
```
