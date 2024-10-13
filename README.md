# Voice cloning bark

<div style="position:relative;width:200px;height:133.33333333333334px;"><iframe src="https://serp.ly/@serpai/badges/ai-alliance" frameborder="0" scrolling="no" width="300px" height="300px" style="position:absolute;z-index:1;"></iframe><a href="https://serp.ly/@serpai/badge-links/artificial-intelligence-alliance" title="" target="_blank" style="display:block;position:absolute;width:100%;height:100%;z-index:2;"></a></div>

https://serp.ly/@serpai/badge-links/artificial-intelligence-alliance

<div style="position:relative;width:200px;height:133.33333333333334px;"><iframe src="https://serp.ly/@serpai/badges/free-ai" frameborder="0" scrolling="no" width="300px" height="300px" style="position:absolute;z-index:1;"></iframe><a href="https://serp.ly/@serpai/badge-links/artificial-intelligence-alliance" title="" target="_blank" style="display:block;position:absolute;width:100%;height:100%;z-index:2;"></a></div>

---

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
