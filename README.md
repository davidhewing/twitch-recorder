# twitch-recorder

Python Script to automatically archive Twitch streams, checking periodically to see if channel is live. Adapted from an old blog post, using newer Twitch API and other minor tweaks. [How to Record Twitch Streams Automatically in Python](https://www.godo.dev/tutorials/python-record-twitch/).  

This version is further enhanced from [rashdanml/twitch-recorder](https://github.com/rashdanml/twitch-recorder) and other copies of this script from sources around the internet.

## Setup

- Clone the repository
- Rename config-example.py to config.py
- Obtain ClientID and ClientSecret from dev.twitch.tv by creating an application with the "Browser Extension" type, update config.py with it.
- Create virtual environment, install dependencies from requirements.txt

### Key dependencies
- ffmpeg
- streamlink

## Usage
Run: 
`python twitch-recorder.py -[s|u] [username] -q [quality]` from within the virtual environment. 

If username and quality not specified, script defaults to `self.username` and `self.quality` specified in twitch-recorder.py 

### Options
- `-s / -u username`           - Stream username to record.
- `-p / --directory directory` - Directory where to write the recording.
- `-l / --log logfile`         - File where to log events.
 

### Quality options

Available options depend on the stream, which can be checked by running `streamlink`. Options: best, 1080p, 720p, 480p, 360p, etc. **best** selects the highest available. 
