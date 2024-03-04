# TRS-80 Color Computer Waveform Generator (CoCoWG)

***
## What does CoCoWG do?

CoCoWG is waveform table generator for the TRS-80 Color Computer, specifically building 256-byte waveform table for use with audio players using the Color Computer's 6-bit DAC. This utility was initially designed to support a 4-voice interrupt driven background player, with waveform table values between 0-63 decimal. The 4-voice players work by adding 4-separate waveforms values together to create a single 8-bit value to send out the DAC (the lower two-bits are ignored leaving a 6-bit value).

The utility provides you with several preset waveforms, but also allows you to customize the properties of individual harmonics to create an unlimited number of possibilities.

## How does CoCoWG create the waveforms?

CoCoWG uses a technique called additive synthesis to generate dynamic waveforms. In additive synthesis, you start out with nothing and build a sound by combining multiple sine waves of differing levels and frequencies. As more sine waves are combined, they begin to generate additional harmonics. In most additive synthesizers, each set of sine waves is viewed and used much like an oscillator.

## What are the limitations of CoCoWG?

Currently, CoCoWG is hard-coded with a FIRQ interrupt driven audio player - therefore its test output files are only compatible with VCC (CoCo 3 emulator).

## How do I get started? All of the 'Test' buttons are greyed-out.

To take full advantage of CoCoWG's testing capabilities, you must pair it with the 'Color Computer 3' VCC emulator (https://github.com/VCCE/VCC). The CoCoWG utility builds dynamic executable binary files, where the VCC emulator is then used to directly test those .BIN files.

Upon the first execution of CoCoWG, there will be an 'cocowg.ini' file created in the root of the application folder. Edit the 'VCC File Path' to target the location of your VCC.exe file. Save the updated 'cocowg.ini' file and re-open the application.

In addition, there is a brief walkthrough of the utility on YouTube - https://youtu.be/rTq5EUAgGmE

## Can CoCoWG be used to create other size waveforms or tables with values higher than 63?

Yes - most certainly. The limitations on the waveform table size are between 16-256 bytes, with waveform table values being 8-bit unsigned integers (0-255).

However, modifying these values outside of the 'preset' values will most likely have adverse effects on the 'Test' playback quality. With waveform table sizes less than 256-bytes, while it may be suitable for your particular application, it will be concatenated to build a full 256-byte waveform table for the purpose of 'Testing' within the emulator.

Likewise, modifying the maximum waveform table values, again while possibly useful for your application, could potentially compromise audio fidelity in the 'Testing' playback within the emulator. Values lower than 63 will decrease the volume of the audio playback while also increasing the noise floor, where values greater than 63 will most likely overflow the output to the DAC (4 separate waves added together), creating clicking/popping or unwanted distortion.

## CoCoWG is a Windows application - will you release a Mac or *nix version in the future?

The short answer - probably not. The longer answer, I'm not a developer (at least not in a true definition sense). I have the ability to hack and cobble together apps/tools/utilities for my specific needs and have never gotten into the practice of cross-platform support. 

## How can I help support the project?

I'm always looking for feedback and suggestions. Please touch base with me on any bugs you might find, or if you have thoughts on how to improve the utility. Also, documentation is currently non-existent for the application. If you would like to help in documenting the application, I'd certainly welcome the support.