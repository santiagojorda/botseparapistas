# Music source separation bot
---
This project arises from the need to learn music through audio tracks where all the instruments are embedded in it. by this traditional learning method, it is common to lose track the instrument we're paying attention because other sounds may interfere.
Based on this neccesity, I have looked for a method to obtain a clean track (or as clean as possible) of that single instrument to follow in my rehearsals.

In this link there is a thread with an example of what I am talking about:
https://twitter.com/sjorda_/status/1452610639482949633

i have found an algorithm called Demucs, created by Facebook researchers, it can separate drums, bass, and vocals from the rest sounds. Demucs works by detecting complex patterns in sound waves, building a high level of understading of which waveform pattern belongs to which instrument or voice and then separanting them.

demucs repository:
https://github.com/facebookresearch/demucs

Demucs can be hard to execute if you are unfamiliar with programming or executings commands on terminal, so the idea of the bot is making that work easly and bring out the posibility of separating tracks without effort. The bot is already running on Twitter and there are instructions about how to use it.

The Bot reads mentions on Twitter on a regular basis of 20 minutes in which a song has been passed as a Youtube link (for now, it will be changed in the future), downloads the video and convert this into an audio file (YoutubeDl Api). The script execute Demucs passing the audio file path recently extracted which will take a few minutes.
When this is done, the Bot will upload the audio files to FileStack and then it will be replying the original tweet incluying the FileStack URLS of those are uploaded. 

# how to implement a bot:
Get a credentials file called credentials.py with this variables:
- access_token
- access_secret
- consumer_secret
- consumer_key
You can generate this values from TWITTER'S API page after register your proyect.

# how to install it:
(this will change with a one line command or executing for first time executing, and if this is executed from outside anaconda shell, it will open a execute it)

## For Windows ussers:
If you are using Windows, replace python 3 by python.exe in all the commands provided in the future

Parts of the code are untested on Windows. If you don't have much experience with Anaconda, python or the shell, here are more detailed instructions. 

Demucs is not supported on 32bits systems

Install Anaconda with Python 3.7 or more recent, you can find it here: https://www.anaconda.com/products/individual#windows
start the Anaconda prompt
Type the followings commands

- git clone -b main --single-branch https://github.com/facebookresearch/demucs ./demucs
- cd ./demucs
- conda env update -f environment-cpu.yml

# installing Libraries: 

## Tweepy
The easiest way to install the latest version from PyPI is by using pip:

- pip install tweepy
or
- git clone https://github.com/tweepy/tweepy.git

## YoutubeDL
- pip install youtube-dl

## Filestack
- pip install filestack
or 
- git clone https://github.com/filestack/filestack-python

