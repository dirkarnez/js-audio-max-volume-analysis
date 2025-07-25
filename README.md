[js-audio-max-volume-analysis](https://dirkarnez.github.io/js-audio-max-volume-analysis)
========================================================================================
### Tutorials
- [Web Audio API](https://webaudioapi.com/book/Web_Audio_API_Boris_Smus_html/toc.html)
  - [ch03 | Web Audio API](https://webaudioapi.com/book/Web_Audio_API_Boris_Smus_html/ch03.html)
```javascript
function findMaxVolume(audioBuffer) {
    let maxVolume = 0;

    // Loop through each channel
    for (let channel = 0; channel < audioBuffer.numberOfChannels; channel++) {
        const channelData = audioBuffer.getChannelData(channel);

        // Loop through each sample in the channel
        for (let i = 0; i < channelData.length; i++) {
            const sampleValue = Math.abs(channelData[i]); // Get absolute value
            if (sampleValue > maxVolume) {
                maxVolume = sampleValue; // Update max volume
            }
        }
    }

    return maxVolume;
}

```
