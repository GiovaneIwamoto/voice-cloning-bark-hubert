# Voice cloning bark

pip install pip==23.2.1

If you encounter an issue while running the cell below, and the error is related to:

ValueError: mutable default <class 'fairseq.dataclass.configs.CommonConfig'> for field common is not allowed: use default_factory

You can resolve this by installing Fairseq using the following command:

%pip install git+https://github.com/One-sixth/fairseq.git

If you then encounter the error:

OSError: [WinError 1314] The client does not have the necessary privilege: '..\\examples' -> 'fairseq\\examples'
...
note: This error originates from a subprocess, and is likely not a problem with pip.

You should run the installation command in the terminal using administrator privileges in PowerShell, rather than in the terminal within VS Code.
