# jsEDF
JavaScript reader of EDF+/BDF+ files

**Usage**
```html
var bytes = UInt8Array(); //Acquired some how (e.g. from input-file or server-based)

var edf = new EDF(bytes);

console.log("DateTime:", edf.date, edf.time);
console.log("Duration:", edf.duration, "seconds");
console.log("Has annotations:", edf.has_annotations);
console.log("Channel count:", edf.realChannelCount);

for (var i = 0; i<edf.realChannelCount; i++)
{
   console.log("> ", i, edf.channels[i].label);
}

var startSecond = 1;
var lengthSeconds = 5;

//Reading data from all channels [[], [], []] 
var data = edf.read(startSecond, lengthSeconds);

var channelIndex = 1;
//Reading data from one channel
var singleChannelData = edf.readSingleChannel(channelIndex, startSecond, lengthSeconds);
```

**Demo**

https://neurobotics.ru/nt/edf/

or just open *demo.html* from this repo
