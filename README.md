# twitch-recorder

Python Script to automatically archive Twitch streams, checking periodically to see if channel is live. Adapted from an old blog post, using newer Twitch API and other minor tweaks. [How to Record Twitch Streams Automatically in Python](https://www.godo.dev/tutorials/python-record-twitch/)

## Setup

- Clone the repository
- Rename config-example.py to config.py
- Obtain ClientID and ClientSecret from dev.twitch.tv by creating an application, update config.py with it. 
- Navigate to Twitch.tv, login, and use the browser development tools to find the cookie named "auth-token" and copy its value to config.py
- Create virtual environment, install dependencies from requirements.txt

### Key dependencies
- ffmpeg
- streamlink

## Usage
Run: 
`python twitch-recorder.py -[s|u] [username] -q [quality]` from within the virtual environment. 

If username and quality not specified, script defaults to `self.username` and `self.quality` specified in twitch-recorder.py 

### Quality options

Available options depend on the stream, which can be checked by running `streamlink`. Options: best, 1080p, 720p, 480p, 360p, etc. **best** selects the highest available. 

### NOTE
The auth-token needs to be updated monthly.  Streamlink is using a different Twitch API than the application API.  Once a fix is found, this may no longer be required.
