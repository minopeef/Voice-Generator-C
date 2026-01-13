# vice-generator-c#
A nine voice polyphonic synthesiser



Vice Generator
Version 0.0

Polyphonic 18 oscillator (9 sinusodial, 9 sawtooth) alias-free synthesiser with a sinusodial LFO modulating the frequency of each oscillator, a cubic distortion unit, and a third-order lowpass Elliptic (Cauer) filter. See the documentation for more information on the signal path.


developed by Visstup (Rittik Wystup)
Compiled by Faust
<http://faust.grame.fr>

This project won the Faust Student Award 2018. Many thanks to the jury for deciding on this project! :)

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as
published by the Free Software Foundation.
<https://www.gnu.org/licenses/lgpl-3.0.en.html>

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.



Build instructions:

Within the command line compiler (Terminal for OS X), go to the directory containing "vicegenerator.dsp" and simply type [faust2vsti vicegenerator.dsp]. The compiled plug-in should appear in the same location as the Faust source (only applicable to Faust users).

IMPORTANT:
"vicegenerator.vst" from the package was created with Faust 2.5.10. If you use a newer version of Faust to compile the synth from source, bear in mind that the "sustain" function in the envelopes library has changed, which means you have to remove the multiplication of 100 in line 107 within the source code. Otherwise, the synthesiser will have some serious amplitude.


Installation instructions (placing):

Place vicegenerator.vst to your VST directory.
~/Library/Audio/Plug-Ins/VST (Mac)

C:\Program Files\VSTPlugins (Windows) - use vicegenerator.dll
// if this doesn't work out, see the suggestions on the Steinberg website:
<https://helpcenter.steinberg.de/hc/en-us/articles/115000177084-VST-plug-in-locations-on-Windows>
— unfortunately, the .dll compiled by the Faust online editor is faulty. Sorry Windows users, I will fix this in the future.

usr/lib/vst (Linux)



If you do not want to build the software from source, simply follow the installation instructions.



Known issues:
The parameters freq, gain, and gate are UI elements which react to MIDI, they should be ignored if you intend to use the synth with MIDI data.
Since this is v0.0 these parameters still appear in the UI, future development will remove them.
The synth sometimes sets the attack time of the envelope to roughly 500ms. I will fix this in the future.
The distortion (thickness) is NOT alias-free, this will be fixed in the future as well. The slider for the filter cutoff frequency is logarithmically mapped; the number box shows linear values, so ignore them. Trust your ears.

Do not rename [vicegenerator.vst] or [vicegenerator.dll], if you do so, your DAW will not find it and you will not be able to use it.

The package contains two audio demos of the synthesiser:
ViceGenerator_inAction.mp3 - a raw unedited demo of the synthesiser
Fraction_Premaster.mp3 - a track I created, using only the Vice Generator as a pitched synthesis source (see the documentation for more details).

I also have a clip on YouTube demonstrating the synthesiser.
https://youtu.be/3uzxZlojxuI


If you find any further problems or have any questions please let me know.
// rittik.wystup@gmail.com

For nerds:
vicegenerator_blockdiagram.svg is a block diagram created by Faust. Open in your browser to view the signal path of the synth.
See vicegenerator.cpp for the Faust-generated C++ code.
See vicegenerator.dsp for the Faust source.
See vicegenerator.txt for a text-version of the Faust source.

Happy music making / source code hacking :)




