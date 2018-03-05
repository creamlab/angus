# README #

angus
https://github.com/creamlab/angus

version 1.0
March 2018

angus (highway to yell) is a real-time voice transformation tool able to simulate cues of arousal/roughness on arbitrary voice signals with a high degree of realism. 
Vocal roughness is generated by highly unstable modes of vibration in the vocal folds and tract, which result in sub-harmonics and nonlinear components which are not present in standard phonation. We propose to simulate this physiological mechanism using multiple amplitude modulations driven by the fundamental frequency of the incoming sound.

### DEPENDENCIES ###
yin~ Max object, analysis and estimation of the fundamental frequency of real-time audio. 
The object is part of the Max Sound Box, distributed on http://forumnet.ircam.fr/product/max-sound-box-en/

### HOWTO ###

# INPUT SOUND

The upper left box in angus allows to specify the audio input: if the microphone is ON, the input gain can be controlled with the dedicated slider, and soundfiles are disabled.
If the microphone is OFF, click on the [OPEN] button to load a soundfile 


# AMPLITUDE MODULATION

Setting parameters for multiple f0-driven amplitude modulation:

* [number of modulators], each one generating two symmetrical sidebands around each partial
* [sub-harmonics interp time]: time for smooth transitions between close sidebands when changing the number of modulators
* [noise amp] and [noise smooth]: add noise on the modulators’ frequencies, by specifying a parameter noise amp that is multiplied by the estimated f0 and then by the noise value itself (varying between 0 and 1 at audio sample rate). This noise component can be then low-pass filtered, with the parameter noise smooth, specifying the period of the filter in milliseconds.
* temporal envelope on top of the waveform, to dynamically control the effect’s
level
* [envelope duration]: duration of the temporal envelope, given by the soundfile duration by default
* modulators' gain: each slider controls the gain of sidebands generated by a given modulator
* modulators' high-pass filtering: each slider controls the cut frequency for high-pass filtering of sidebands generated by a given modulator

# PRESETS

All of the parameters can be organized in presets and subsequently recalled and interpolated in real-time. 

* recall a preset: use the panel with small squares, each square is a preset; pass upon a lighted square with the mouse to know the preset’s name, click on a square to recall a preset

* fading between two presets: select [START] / [END] presets and a [FADE] time to dynamically change from a preset to another

* define a preset: 
- define a sliders and parameters configuration you want to store
- type the preset name in the text box
- the software automatically proposes a preset number that can be used (current limit is 60 presets) 
- hit the [SAVE AS PRESET <n>] button

* overwrite a preset (presets from 1 to 9 cannot be modified): 
- recall a preset
- define a new sliders and parameters configuration you want to store
- optionally type a new preset name in the text box
- hit the [OVERWRITE PRESET <n>] button

* the [SHOW] button provides a list of the available presets and parameters that are controlled

* the [LOAD] button allows to load a .json file of presets (e.g. to replace the standard .json file distributed with DAVID with other presets saved from previous versions of the software)


### Who do I talk to? ###

* marco.liuni@ircam.fr
* cream.ircam.fr
