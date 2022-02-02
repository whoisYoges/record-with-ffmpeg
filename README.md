### record-with-ffmpeg

Record your desktop audio, microphone and  video in any linux from terminal.

## Features
- fully command line tool
- Different options for recording
    - Internal/monitor audio only
    - Microphone only
    - Both internal audio and microphone
    - Video only (without audio)
    - Video with internal audio
    - Video with microphone
    - Video with both internal audio and microphone

### Dependencies
- pulseaudio
- ffmpeg

### Installation and Usage

Check, edit and confirm all the variables listed below in [record-with-ffmpeg](record-with-ffmpeg).

- videodir // location to save the recorded videos
- audiodir // location to save the recorded audio
- recordingresolution // resolution of your monitor or specific area of monitor you want to record
- outputresolution // output video resolution (recommended <= recordingresolution)

#### Audio Inputs  
Get these audio input names using `pactl list sources` command under `Name` section in terminal.
- monitoraudioinput // internal/system/monitor audio
- microphoneaudioinput // external/microphone audio

also check ac and ar value using `pactl list source` command under `Sample Specification` section
for eg: if output has:: `Sample Specification: s16le 2ch 48000Hz`
then ac is 2 (i.e, audio channel) and ar is 48000 (i.e, audio frequency)
- monitoraudiochannel // number of audio channel of builtin/monitor audio source
- microphoneaudiochannel // number of audio channel of microphone
- monitoraudiofrequency // audio frequency of builtin/monitor
- microphoneaudiofrequency // audio frequency of microphone
- outputaudiofrequency // output audio frequency (recommended: smaller among audio inputs)

#### Installation
```
git clone https://github.com/whoisYoges/record-with-ffmpeg \
    cd record-with-ffmpeg/ \
    chmod +x record-with-ffmpeg \
    sudo mv record-with-ffmpeg /usr/local/bin/ \
    cd .. \
    rm -r record-with-ffmpeg
```

### Uninstallation
```
sudo rm /usr/local/bin/record-with-ffmpeg
```

