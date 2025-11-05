Installing Piper-TTS on Mac OSX Sequoia (MacBook Pro M1)

1) Do NOT install Python with Homebrew or with the Python package from website. This doesn't work and will throw up conflicts.
2) Use Homebrew to install Pyenv. (https://mac.install.guide/python/install-pyenv)
3) Install Python with Pyenv. Only install version 3.11 as onnxruntime doesn't currently play nicely with newer versions
4) You might need to install pip. (If so use this guide: https://mac.install.guide/python/install-pip)
5) Make sure that shell is pointing to the Pyenv installed version of python, not the OSX system python 
		
				Add the following at the end of the ~/.zprofile file.
                    export PYENV_ROOT="$HOME/.pyenv"
                    [[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"
                      eval "$(pyenv init -)"

                (Changes to the ~/.zprofile file will not take effect in the Terminal until you've quit and restarted the terminal. Alternatively (this is easier), you can use the source command to reset the shell environment:
		 $ source ~/.zprofile 

6) Install Piper-TTS  via pip:  pip install piper-tts
7) Download voices from https://huggingface.co/rhasspy/piper-voices/tree/main and save them locally on your machine in a sensible place. (I use $User/piper/voices/en/ (then individual voice files folders)
8) create a plain txt file input. I saved mine in documents
9) use this command to run piper, read the input file and create a wav file output. Note: You musty specify where the voice files are, where the input file is and where the wav file is output to:
	piper --model "$HOME/piper/voices/en/Cori/en_GB-cori-high.onnx" --input-file $HOME/Documents/Piper-Test.txt --output-file $HOME/Documents/piperoutput.wav


