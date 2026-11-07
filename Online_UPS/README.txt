ONLINE UPS SIMULATION PROJECT
OrCAD/PSpice Schematic and MATLAB/Simulink Model

1. PROJECT OVERVIEW
This project compares a circuit-level UPS schematic in OrCAD/PSpice with a simplified, signal-level UPS model in MATLAB/Simulink. The Simulink model illustrates the signal flow and control logic; it is not a detailed switched power-electronics or electrochemical battery simulation.

2. SOFTWARE REQUIREMENTS
A. MATLAB / Simulink model
- MATLAB R2026b (Version 26.2) is the version used for the project guidance and report.
- Simulink R2026b (Version 26.2).
- No Simscape Electrical installation is required for the described signal-level model, provided the model uses only standard Simulink blocks.
- A valid MathWorks license with Simulink access is required. Other MATLAB toolboxes are only required if the actual model uses blocks from them.

B. OrCAD / PSpice schematic
- OrCAD Capture / PSpice installed and licensed, with support for the component models used by the circuit.
- The schematic references a 230 V RMS, 50 Hz source, 1N4007 diode models, MOSFET models, inductors, capacitors, resistors, pulse/gate-drive sources and controlled switches.
- Availability of a specific MOSFET model or library may depend on the OrCAD/PSpice installation. Replace missing models only after checking their electrical parameters.

3. HOW TO OPEN A MATLAB SIMULINK .SLX FILE
1. Install and activate MATLAB with Simulink.
2. Copy the supplied .slx file and any supporting files into one folder on your computer. Keep related files together.
3. Start MATLAB and set the Current Folder to that project folder, or navigate to it using the MATLAB file browser.
4. Double-click the .slx file in the Current Folder panel. Alternatively, type the model filename without the extension in the MATLAB Command Window, for example:
      open_system('Online_UPS_Model')
   Replace Online_UPS_Model with the actual .slx filename.
5. Review the model and check for missing-block or missing-library warnings.
6. Click Run in the Simulink toolbar to simulate. Open the Scope blocks to view waveforms.
7. If prompted to update a model, save a separate copy first if you want to preserve the original.

IMPORTANT: This delivery currently contains a README and reference images of the schematic/waveforms. The native .slx model file was not available in the files provided for packaging, so it is not included in this package. The images are for reference only and cannot be opened as editable circuit/model files.

4. HOW TO OPEN THE ORCAD SCHEMATIC
1. Install and launch a compatible version of OrCAD Capture/PSpice.
2. Open the native OrCAD project or design file from File > Open (commonly .opj and/or .dsn, depending on the project version and structure).
3. Ensure required simulation profiles, libraries and device models are available.
4. Run the PSpice simulation from the project/design environment and open the Probe waveform window to inspect the output.

IMPORTANT: A native OrCAD .dsn/.opj project was not available in the files provided for packaging. The ZIP contains the supplied schematic and waveform images as visual references, not an editable or runnable OrCAD project.

5. MODEL NOTES / LIMITATIONS
- The Simulink model described in the report uses standard Simulink signal blocks and an idealized 400 V constant as a battery-backed DC-source representation.
- It demonstrates functional signal flow, source selection and an AC-like output waveform; it does not by itself validate real battery charging, battery runtime, semiconductor losses, thermal behaviour, protection, efficiency or hardware safety.
- The OrCAD output waveform should be treated as the result shown in the supplied reference, not as proof of performance beyond the simulation evidence available.
- Do not connect this model directly to real mains or hardware. Hardware implementation requires qualified engineering review, isolation, protection and appropriate laboratory safety procedures.

6. FILES IN THIS PACKAGE
- README_Online_UPS_Project.txt — setup and opening instructions.
- OrCAD_UPS_Schematic_Reference.png — supplied OrCAD schematic screenshot.
- OrCAD_UPS_Output_Waveform.png — supplied OrCAD output waveform screenshot.
- Simulink_UPS_Model_Overview_1.png — supplied Simulink model overview screenshot.
- Simulink_UPS_Model_Overview_2.png — supplied Simulink model overview screenshot.
- Simulink_UPS_Output_Waveform.png — supplied Simulink output waveform screenshot.

Prepared for the Online UPS Simulation project.
