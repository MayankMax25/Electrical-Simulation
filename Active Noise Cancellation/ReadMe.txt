Adaptive Frequency-Domain Active Noise Cancellation (ANC)

A MATLAB/Simulink project exploring acoustic noise reduction using FFT/IFFT processing and RMS-error-based adaptive gain control.

Overview

The project simulates an Active Noise Cancellation system using two audio inputs: a desired audio signal and an unwanted noise signal.

The noise is processed in the frequency domain to generate an anti-noise component. An adaptive gain mechanism adjusts its amplitude using RMS-based error feedback. The processed signal is then reconstructed and combined with the input audio to obtain the ANC output.

Sampling Frequency: 44.1 kHz

System Workflow

Audio Input + Noise Input
          |
          v
     Noise Scaling
          |
          v
     FFT Processing
          |
          v
  Convolution / Inversion
          |
          v
  Adaptive Gain Control
          |
          v
    Anti-Noise Generation
          |
          v
         IFFT
          |
          v
    Signal Combination
          |
          v
       ANC Output

A feedback mechanism monitors the RMS-related error and controls the gain of the generated anti-noise.

Adaptive Gain Logic

The MATLAB Function block uses the following update rule:

function output = fcn(err,oldgain)

req_err = 0.0001;

if(req_err <= err)
    output = oldgain + 0.005;
else
    output = oldgain;
end

end

The gain increases by 0.005 when the measured error reaches the specified threshold; otherwise, it retains its previous value.

Technologies Used

MATLAB

Simulink

Fast Fourier Transform (FFT)

Inverse FFT (IFFT)

RMS-based feedback

MATLAB Function Block

Repository Contents

Model/ – Simulink model (.slx)

Audio/ – Desired audio and noise input files

Results/ – Simulink diagrams and output waveforms

Documentation/ – Project paper and technical documentation

Running the Project

Clone or download this repository.

Open MATLAB and navigate to the project folder.

Open the Simulink model.

Check the paths of the input audio files.

Run the simulation and observe the ANC output.

Ensure that the required audio files and MATLAB/Simulink dependencies are available.

Base Research Paper

A Simplified Subband ANC Algorithm Without Secondary Path Modeling

Min Gao, Jing Lu, and Xiaojun Qiu
IEEE/ACM Transactions on Audio, Speech, and Language Processing, Vol. 24, No. 7, pp. 1164–1174, July 2016.

DOI: 10.1109/TASLP.2016.2516439

The paper investigates a simplified subband ANC approach that avoids explicit secondary-path modeling. It serves as the primary research reference for this project.

Implementation Note: This project uses a simplified FFT/IFFT-based architecture with RMS-error-based adaptive gain control. It is not a direct implementation of the SSANC algorithm proposed in the reference paper.

Limitations and Future Work

Current implementation is simulation-based.

Adaptive gain adjustment uses a simple threshold-based approach.

Quantitative evaluation using SNR, MSE, and other performance metrics remains to be explored.

Future extensions include improved adaptive algorithms, microphone-based real-time operation, and hardware implementation.

Author

Mayank Pal
B.Tech. Electrical and Electronics Engineering
Vellore Institute of Technology (VIT), Vellore, India
