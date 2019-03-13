# mpseek

Conditional search queries for Music Player Daemon (MPD).

## Usage

`$ mpseek '[condition] [keywords...]'`

## Examples:

```sh

    $ mpseek jazz

    $ mpseek "michael jackson" album!=thriller

    $ mpseek "genre=mpb|latin|soca brazil"

    $ mpseek 'genre="hip hop" && date>1990'

    $ mpseek "( genre=funk || album=funk ) && file=flac$"
```

## Dependencies

 - `bash`
 - `awk`
 - `xargs`
 - `mpc`
