## Create a duplicate line shortcut for jupyter notebook:

**1.** (optional) If not exists: create a folder custom:
>`$mkdir ~/.jupyter/custom`<br>
**2.** Run ~/mnt/.jupyter/dupl_line.sh file:
`$bash ~/mnt/.jupyter/dupl_line.sh`<br>
**3.** Restart jupyter notebook.<br>
**4.** Copy the following lines into the jupyter notebook and run to test if the js file is in the correct place:

        from jupyter_core.paths import jupyter_config_dir
        
        jupyter_dir = jupyter_config_dir()
        jupyter_dir
        # Should output -> '/home/ubuntu/.jupyter'
        
        import os.path
        custom_js_path = os.path.join(jupyter_dir, 'custom', 'custom.js')
        custom_js_path
        # Should output -> '/home/ubuntu/.jupyter/custom/custom.js'
        
        # my custom js
        if os.path.isfile(custom_js_path):
            with open(custom_js_path) as f:
                print(f.read())
        else:
            print("You don't have a custom.js file")

**5.** Place a cursor next to the line you want to duplicate or select the line and press `Ctrl+D`
