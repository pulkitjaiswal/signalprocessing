signal processing javascript library (peak analysis from DNA sample)
================
Modules:

  DFT(bufferSize, sampleRate): Discrete Fourier Transform

    Usage: 

    var dft = new DFT(1024, 44100);
    dft.forward(signal);
    var spectrum = dft.spectrum;


  FFT(bufferSize, sampleRate): Fast Fourier Transform

    Usage:

    var fft = new FFT(2048, 44100);
    fft.forward(signal);
    var spectrum = fft.spectrum;


  Oscillator(waveform, frequency, amplitude, bufferSize, sampleRate): Signal Generator
    * Sine wave
    * Square wave
    * Saw wave
    * Triangle wave

    Usage:

    var osc = new Oscillator(SINEWAVE, 440, 1, 2048, 22050);
    osc.generate();
    var signal = osc.signal;


  ADSR(attack, decay, sustainLevel, sustain, release, sampleRate): Attack-Decay-Sustain-Release Envelope
    
    Usage:

    var envelope = new ADSR(0.01, 0.1, 0.5, 0.1, 0.2, 44100);
    envelope.process(signal);


  IIRFilter(filter, cutoff, sampleRate): Infinite Impulse Response Filters
    * Low Pass Filter
    * High Pass Filter

    Usage:

    var filter = IIRFilter(LOWPASS, 200, 44100);
    filter.process(signal);


  MultiDelay(maxDelayInSamplesSize, delayInSamples, masterVolume, delayVolume): Delay which feeds back its own delayed signal	
  
    Usage:

    var delay = MultiDelay(44100*5, 44100*1, 1.0, 0.6);
    delay.process(signal);  
    

  Reverb(maxDelayInSamplesSize, delayInSamples, masterVolume, mixVolume, delayVolume, dampFrequency): Reverb
  
    Usage:

    var reverb = Reverb(20000, 6500, 0.8, 0.5, 0.9, 4500);
    reverb.process(signal); 
