---
layout: page
title: Pulseaudio 
permalink: /linux/recording.html
---

Create 1 null sink and 2 loopbacks devices with
- `pactl load-module module-null-sink sink_name=mysink`
- `pactl load-module module-loopback source=alsa_output.pci-0000_00_1f.3.analog-stereo.monitor sink=mysink`
- `pactl load-module module-loopback source=alsa_input.pci-0000_00_1f.3.analog-stereo sink=mysink`

- Check that everything is setup correctly in pulseaudio UI [pavucontrol]
- Record audio from speaker and microphone at the same time
	- `arecord -f S16_LE -c1 -r22050 -t raw | lame -r -s 22.05 -m m -b 64 - Output.mp3`
	- inside pavucontrol select as recording devices the null sinkm where mic and speaker fluxes are goining into.
