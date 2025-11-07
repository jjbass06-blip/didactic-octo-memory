Use the work book here: https://colab.research.google.com/drive/1-1hXWc1YmiRu0kkeFw5rsGwJ8zQ0ykmZ

0) Run the Colab Runtime +GPU check. Using free version means sometimes the GPU isn't immediately available
1) Run step 1 to install system pkgs  and espeak
2) Run step 2 to clone the repo and go into working directory of repo
3) Run step 3 to install the Piper application
4) Run step 4 to run the monotonic align shell script
5) Run step 5 to run other dependencies
6) Run step 6 to mount your Google Drive for transfer of wav files and others. Inside MyDrive create a new folders called /TTS Data/myvoice/wavs. You can call it whatever you want but it needs to match the data root variable in step 7. Put all your wav recordings in this folder. In the my voice folder put your metadata.csv file (this should contain transcripts of each file recroding so the AI engine can match the text to the wav recordings
7) Run step 7 to set the variables to the folder paths
8) Run step 8 just as a safety check to see if the transcript can be seen for the first 5 files
9) Run step 9 to start ther training. (It will use an exisitng Piper checkpoint so this is essentially fine tuning. You can let this run for as long as you want. You will see it updating checkpoints in the LH browser of Colab in the lightning _logs/version_0/checkpoints folder)
10) When you have decided to stop the training, click the 3 dots next to the checkpoint to copy the path and paste it into step 10. The run step 10 to generate the Onyx file. It will store in the root folder.
11) Run step 11 to export the corresponding .json file. It will export this to the root folder too.
12) Doewnload these two files and use them with Piper :)
