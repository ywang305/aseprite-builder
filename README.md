# aseprite-builder
Build Aseprite using Github action

# What should you do?
- fork this repo
- **enable workflow `Build and release Aseprite` in `Actions -- Workflows`**
- click `Action > Build and release Aseprite > run workflow` as the figure shows
  ![trigger the workflow](https://github.com/user-attachments/assets/5174f407-4daf-4e28-996e-5efb4f8751cb)
  
- now you should see the building process via `Actions` and you can find the product in `Release`

accroding to [Eula](https://github.com/aseprite/aseprite/blob/main/EULA.txt) :

> (b) Distribution.
> 
> You may not distribute copies of the SOFTWARE PRODUCT to third parties. Evaluation versions available for download from the Licensor's websites may be freely distributed.

we need to remove the product in `Releases` .


# Install
- download the trial from official, download the build from this release
- install trial
- run script to replace partial folders in trial with the release, using script ( or manuualy ) \
    ```rb
      sh "rm -rf ./Aseprite.app/Contents/MacOS/aseprite"
      sh "cp -r ./aseprite/build/bin/aseprite ./Aseprite.app/Contents/MacOS/aseprite"
      sh "rm -rf ./Aseprite.app/Contents/Resources/data"
      sh "cp -r ./aseprite/build/bin/data Aseprite.app/Contents/Resources/data"
    ```  
