# Ultra96V2_Blinky
In this tutorial we will run the Blinky script I created Via Bare Metal and cross compiling on the Ultra96V2 Development Board.
Feel free to download the program above as you follow this tutorial.

We will be able to blink the 4 configurable LEDS near the top of the board that are assigned to MIO17 - MIO20
## Pre-requisires
- [Setting Up VM Environment](https://github.com/abdoo8080/tutorials/blob/main/virtual_machine_setup/tutorial.md)
- [Install Vitis and Vivado IDEs](https://github.com/abdoo8080/tutorials/blob/main/install_vitis_and_vivado/install_vitis_and_vivado.md)
- [Connecting your Ultra96V2 to the Serial Monitor. (GTKTerm)]
- [Hello World Cross-Compile](https://github.com/jramey2016/HelloWorld_CrossCompile_Ultra96V2)

# Steps

1.) We will start by launching the Xilinx Vitis IDE. Upon launch you will be asked to select your workspace directory. Click Launch.

![direct](https://user-images.githubusercontent.com/72533453/129287452-0ce2adbe-43fa-4b6e-b103-291c38e977dd.PNG)

2.) Once the Vitis IDE launches go to New > Application Project.

![App](https://user-images.githubusercontent.com/72533453/129287540-d15beaa9-22a3-4460-bcdb-3e096414513f.PNG)

3.) Click Next throught the welcome page, and Selsct, "Create a new platform from hardware (XSA)" Browse to find the desired XSA file.

![XSA](https://user-images.githubusercontent.com/72533453/129287662-aae5e929-c284-4c27-b044-88aa83918c8d.PNG)

4.) Name your Application make sure the processor choosen is "psu_cortexa53_0" 

![project](https://user-images.githubusercontent.com/72533453/129287803-4cd78bf7-7878-4e88-b13a-be77e1b13366.PNG)\

5.) Choose your template (Preferably the Hello World option) and click finish. May take a little bit to generate the platform

![temp](https://user-images.githubusercontent.com/72533453/129287886-69d8a914-7d46-4d52-bacf-b0e1f245ff10.PNG)

6.) Once the platform is generated, navigate to platform.spr > Board Support Pacakages > Modify BSP Settings...

![BSP](https://user-images.githubusercontent.com/72533453/129288133-02c5968f-808c-4557-aaf5-c11a0855cea6.PNG)

7.) Once the window pops up, select standalong on the side tab, change the stdin and the stdout values to psu_uart1. MAKE SURE TO DO THIS OR YOU WILL NOT GET AN OUTPUT.

![uart](https://user-images.githubusercontent.com/72533453/129288280-ec696d28-7714-448e-bbd0-d84875e7aaa7.PNG)

8.) Next you will notice that the project has (Out-of-date) next to it. Select the project and hit build icon on the top tab. This will take a minute or two.

![out of date](https://user-images.githubusercontent.com/72533453/129288430-5128904e-143f-49c9-9192-2c173761a19d.PNG)

9.) Now head to your src file in the Blinky directory and you should see your helloworld.c program. Launch your Serial Monitor and run the hello world script to make sure you are set. If you are not ready for this step refer to the GTK term tutorial above. 
SIDE NOTE: for the bare metal application to run ensure that both of the dip switches on the Ultra96 are switched to the ON posiistion!!!

![BE37C9DD-D9C4-448F-9410-14B9BF12FD19](https://user-images.githubusercontent.com/72533453/129291561-f2675400-1a7d-4fee-b501-6b39ce70a6e7.jpeg)


10.) The next step is to build the script. Once that has completed Launch the program on hardware. SO select the application name in this case right click on blinky > Run As, Launch on Hardware. Once you launch the program there will be a read out on the Serial Mointor and all four of the user configurable LEDS will blink.

![BD28B9F5-7A43-4F38-BEF3-813B0B99DDFA](https://user-images.githubusercontent.com/72533453/129291563-9a6c537a-9ede-4253-b070-be1337c87e1c.jpeg)
