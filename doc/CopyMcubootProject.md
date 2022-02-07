# How to copy MCUboot into your own workspace folder

Video:  
- English =>  ---
- Deutsch =>  ---


**Note:** There is the possibility to do a Multi-Image build, which allows to build a project that includes MCUboot beside the application. Using Multi-Image build is the standard way to include MCUboot into an application project. In this chapter I talk about how to create a MCUboot project copy, that only includes the MCUboot software. For completness, I will also point to an example that takes care about downloading the firmware image, which is done in the application software.

## How to copy the MCUboot project

It is usually quite easy to copy a Zephyr project. All needed information to build the project files are defined in the CMakeLists.txt file. And an own project just needs to know where the Zephyr project software modules are stored. 

MCUboot is different. The MCUboot repository includes all needed software modules. Because of this there are several software module folders in the bootloader directory and the MCUboot project uses this via relative path definitions. So it is important to use the same folder structure when you want to copy the project into your own workspace (or you have to modify the CMakeLists.txt file). 

So the easiest way to copy the MCUboot project is to copy the complete mcuboot folder:

            /bootloader/mcuboot


## Where is the MCUboot project folder

The MCUboot project folder can be found here:

            /bootloader/mcuboot/boot/zephyr


## Example project that shows how to download a firmware image

MCUboot is taking care about the boot process. It does not take care about downloading the new application firmware image. This is done in the application.

An example that shows how this can be done in the application is available here:

            zephyr/samples/subsys/mgmt/mcumgr/smp_svr
            
