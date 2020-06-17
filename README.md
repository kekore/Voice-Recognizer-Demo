# Description
**Voice Recognizer Demo**

Author: Eryk Prokopczuk

The program uses evolutionary algorithm to search for neural network hyperparameters close to optimal.
The neural network is later used to recognize defined labels from user's voice recordings.

# Installation
The demo repository contains exe build and installer build:
* Run the .exe file if you have installed LabVIEW or LabVIEW run-time engine.
* Run the installer if you don't have any of the above or if .exe file doesn't work for any reason.

# Demo
Run *Voice Recognizer.exe*. To try out the demo and train two high-accuracy models, two scenarios are proposed:
### Scenario 1 (Total time: 5 minutes)
1. Check your microphone and configure the *Crop percentage threshold* value following the instructions on the right side of the UI. Remember to apply the new value by pressing the *Apply threshold* button.
2. Record your dataset in *CREATING DATASET* section with the following settings:
- Labels: |zero|one|
- Each label x times: 10
- Save folder path: any new and empty folder
3. Press the *Create dataset* button and follow the instructions in the dialog boxes. Pay attention to the recordings played in the background. The quality of the recordings is important. If you don't hear your whole talk, you hear noise at the beginning or at the end of the recording after few tries, configure again the *Crop percentage threshold* value or plug in another microphone.
4. Set the following parameters for the evolutionary algorithm:
- Input size: 10
- Neurons in layers: |3|
- Generation size: 100
- Max weight absolute value: 3
- Recombination percentage: 0.3
- Survival percentage: 0.1
- Mutation percentage: 0.1
- Target efficiency: -0.05
- Max iterations: 500
5. Set the *Dataset folder path* to the folder you recorded your dataset into (in instruction 2.) and the *Model file path* to any new file with *.xml* extension.
6. Press the *Start model training* button. The training should take about 10-20 seconds.
7. After the training you should receive three dialog boxes confirming the success of training, saving to file and loading up the model.
8. Try out the model. Press *Record and recognize* and say *zero* or *one*. Take a look on the model's guesses.

### Scenario 2 (Total time: 10-30 minutes depending on the hardware)
1. Check your microphone and configure the *Crop percentage threshold* value following the instructions on the right side of the UI. Remember to apply the new value by pressing the *Apply threshold* button.
2. Record your dataset in *CREATING DATASET* section with the following settings:
- Labels: |zero|one|two|
- Each label x times: 20
- Save folder path: any new and empty folder
3. Press the *Create dataset* button and follow the instructions in the dialog boxes. Pay attention to the recordings played in the background. The quality of the recordings is important. If you don't hear your whole talk, you hear noise at the beginning or at the end of the recording after few tries, configure again the *Crop percentage threshold* value or plug in another microphone.
4. Set the following parameters for the evolutionary algorithm:
- Input size: 16
- Neurons in layers: |6|4|
- Generation size: 100
- Max weight absolute value: 4
- Recombination percentage: 0.3
- Survival percentage: 0.1
- Mutation percentage: 0.1
- Target efficiency: -0.05
- Max iterations: 130000
5. Set the *Dataset folder path* to the folder you recorded your dataset into (in instruction 2.) and the *Model file path* to any new file with *.xml* extension.
6. Press the *Start model training* button. The training should take less than 15 minutes.
7. After the training you should receive three dialog boxes confirming the success of training, saving to file and loading up the model.
8. Try out the model. Press *Record and recognize* and say *zero*, *one* or *two*. Take a look on the model's guesses.