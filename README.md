# Plugget Unreal plugin

Unreal plugin to search & install [plugget](https://github.com/plugget/plugget) packages 

![image](https://github.com/plugget/plugget-qt-addon/assets/3758308/0752c140-5b26-452e-81ac-fc4e36ccdb23)<br>


## Usage instructions
- Open the Plugget Package Manager from Unreal menu `Edit > Plugget Packages`

How to use:
- Search for plugget packages, click install to install the selected version
- List installed packages with the list button


## Install instructions

<details>
<summary>1. Copy the plugin to unreal's plugin folder</summary>
  
  - [Download](https://github.com/plugget/plugget-unreal-plugin/archive/refs/heads/main.zip) and Unzip  
  - Copy the extracted `plugget` folder to Unreal's plugins folder  
</details>


<details>
<summary>2. Enable the plugin</summary>
  
  - Open the Unreal plugin editor from the menu `edit/Plugins`
  - Enable the `plugget` plugin
  - Restart Unreal
</details>

<br>
Dependencies are auto installed on startup, if that fails try manually:
<details>
<summary>(optional) Manually install Python dependencies</summary>
  
Install the dependencies to Unreal's engine folder:

⚠️ PySide 6.7 has a breaking bug. Install older version for now  
py3.11 has no available older versions for PySide6  

```batch
set UE_FOLDER="D:\Program Files\Epic Games\UE_5.4"
set PYTHON_FOLDER=%UE_FOLDER%\Engine\Binaries\ThirdParty\Python3\Win64
cd /d %PYTHON_FOLDER%
python -m pip install PySide6 --version 6.6.3.1 --target %PYTHON_FOLDER%\Lib\site-packages
python -m pip install plugget-qt --target %PYTHON_FOLDER%\Lib\site-packages
```
</details>


<details>
<summary>(optional) Install git to support git clone package installs</summary>
  
  (plugget uses this to install packages)  
   open the command prompt on Windows and run the below command:  
  
```
winget install git.git
```
</details>



### dependencies
- [plugget-qt](https://github.com/plugget/plugget-qt)
- pip (have python installed and pip in the path)
- git (have git installed and in the path



### Environment variables
you can control how plugget loads on startup with these env vars
- `PLUGGET_UE_TOOL_BAR_BUTTON`: default to `0`, if set to `1`, adds a button to the tool bar to launch the UI 
- `PLUGGET_UE_MENU`:  default to `0`, if set to `1`, adds a menu entry under Tools/Plugget **TODO** ⚠️not yetimplemented, verify path

### devs
- This repo contains the unreal plugin `Plugget`, and no Python modules.
- The Python dependencies it installs are `plugget` & `plugget_qt`

### Support

If this tool is helpfull, you can ⭐ star it on the github page,
just click the ⭐ star button in the top-right of this page.
