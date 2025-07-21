# Comfyui-NukeX
Comfyui Installation and Nuke-Comfy connection mannual


Read carefully and follow the steps one by one

Comfyui Installation and Nuke-Comfy connection mannual





1. Install Latest Python from Python.org

         Note:-Uninstall all the previous Python files and directories. [during the installation check all boxes] othe wise it won't work.

2. Head over to { https://git-scm.com/ } and download git for Windows and Install it.

3. Install ComfyUi into your system

[ https://github.com/comfyanonymous/ComfyUI ] Head over to this website and under installing section click "DIRECT LINK TO DOWNLOAD" and use 7Zip to unzip it.

         Download the " ComfyUI_windows_portable_nvidia.7z " Folder into your desired dir and download the manager(bat file) into the "ComfyUI_windows_portable" folder.
         Run the
         " install-manager-for-portable-version.bat "
         file to install manager after completation Run
         " run_nvidia_gpu.bat " or " run_cpu.bat "
         depending on your pc specs.
      
         If you still can't see your manager in Comfy interface wait for step 10
         wallah comfy is in your system now! now close it for now. 

4. Head over to .nuke folder and one the location pane type "cmd" to open commanline on python { cd "C:\Users\<username>\.nuke" }
   on the terminal type

            { git clone --recursive https://github.com/vinavfx/ComfyUI-for-Nuke nuke_comfyui }

or you can copy paste the "comfyui-for-nuke" folder in .nuke [name the folder "nuke_comfyui"]

5. Install websocket into your system
   Open the terminal as administrator and run

            { "C:\Program Files\Nuke15.1v3\python.exe" -m pip install websocket-client }

7. Add the path to your enviroment variables in your system under (System variables>Path) click new and add the path

8. Follow the terminal if update needed and repeat the step no 5

9. Important step :-

         Open your meny.py and copy the following
         import nuke_comfyui as comfyui
         comfyui.setup()

10. Now it's time to install manager in comfy if you successfully get your manager after step 3 you can skip this step

          open "comfyUi" folder in "ComfyUI_windows_portable" and enter the "Custom_node" Folder
          type "cmd" in location pane and run
          { git clone https://github.com/spacepxl/ComfyUI-HQ-Image-Save.git }
          open "ComfyUI-Manager" folder and type "cmd" in location pane and run
          pip install -r requirements.txt

11. Now install ComfyUI-HQ-Image-Save (required to work with EXR)

          open "comfyUi" folder in "ComfyUI_windows_portable" and enter the "Custom_node" Folder
          type "cmd" in location pane and run
          { git clone https://github.com/spacepxl/ComfyUI-HQ-Image-Save.git }
          open "ComfyUI-HQ-Image-Save" folder and type "cmd" in location pane and run
          pip install -r requirements.txt

    You can also do the step no 11 from your comfy interface from manager by typing "HQ" and installing it


12. Modify environment variables in env.py inside comfy folder (.nuke) :-
    
             COMFYUI_DIR = '<path_to_ComfyUI>' # Put the directory where ComfyUI is installed !
             IP = '127.0.0.1'
             PORT = 8188
             NUKE_USER = '<path_to_.nuke>' # Change only if your path is different !
      


Now run comfyUI in background and start Nuke
Wallah both are connected.

    Tips:-

    If you get any error while opening nuke look for your python in your system is it there or not ensure the version by typing { python --version }
    and then repeat step 4.5.8

    If you want to have the ComfyUI server on another machine, you must share the folder where ComfyUI is installed and put the path in env.py

    To make ComfyUI work with pixel values greater than 1 and less than 0, change tonemap knob to 'linear' in the 'SaveEXR' node

    When connecting any image or roto from Nuke, take into consideration the 'FrameRange' of the output because that will be the batch size.

    
    

    
    
    

