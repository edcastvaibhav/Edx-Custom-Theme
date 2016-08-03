Setup Instructions

1. Create a directory named "custom_theme" inside "/edx/app/edxapp/themes/".
2. Go to the newly created directory using "cd custom_theme".
3. Pull this repository.
4. Modify the lms.env.json file that can be found in the /edx/app/edxapp directory. You can do so with the character-based editor nano, using the following command:
"sudo nano /edx/app/edxapp/lms.env.json"
5. In the JSON file, change “USE_CUSTOM_THEME”: false to “USE_CUSTOM_THEME”: true
Also change “THEME_NAME”: “” to “THEME_NAME”: “custom_theme”.
6. Save the file using "CTRL + 0" & close the file using "CTRL + X".
7. Execute the following commands 
  - sudo su edxapp -s /bin/bash
  - cd ~
  - source edxapp_env
  - cd /edx/app/edxapp/edx-platform
  - paver update_assets lms --settings=aws
  - sudo /edx/bin/supervisorctl restart edxapp: 
9. After the server is restarted, changes for the custom theme should be reflected.

Thanks :)
