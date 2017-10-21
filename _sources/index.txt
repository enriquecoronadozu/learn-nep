.. NEP documentation master file, created by
   sphinx-quickstart on Tue Apr 18 09:58:21 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to NEP's documentation!
===============================

Node primitives (NEP) is an open source experimental platform which allows the creation and design of social interactions with robots. This platform have the next characteristics:

* Cross-plataform: support Linux, Windows and OSX.
* End-user and expert programming platform.
* “Easy to install”, “easy to use” and “easy to develop”.
* Google blocky based for end-user programming.
* Use ZeroMQ for comunication between nodes
* Mostly witten in JavaScript(for code generation) and Python.
* Easy integration with ROS modules.

In the current version the plataform support NAO robot, Kinect V2 (only Windows), Wii Balance Board (only Windows) and IMUs from Android smartwatches/smartphones. 

Instalation
==================

This section describe how to install the platform in diferent operating systems.


Windows
**********************

* Download and install Python(x,y) from: https://python-xy.github.io/

* Download the most recent version of the NEP social robot programming platform from:

* Unzip the folder and run the **install.sh** script (with double click)

.. note:: In order to use the actual modules of **Kinect V2** and **Wii Balance Board** in Windows, it is needed to Install C# from `Visual Studio Community <https://www.visualstudio.com/es/downloads/?utm_source=mscom&utm_campaign=msdocs>`_ . If you are not sure, then install all the components.

.. note:: In order to use **Kinect V2** in Windows, it is also needed to download and install `Kinect SDK V2 <https://www.microsoft.com/en-us/download/details.aspx?id=44561>`_


The platform have been tested in Windows 8.1 and Windows 10 and using Visual Studio Community 2013 and 2017 for the Kinect and Wii Balance Board devices.

Linux
**********************

* Download the most recent version of the NEP social robot programming platform from:
* Open the linux console and run the **install.sh** script

.. warning:: There is not a Kinect V2 and Wii Balance Board compatible nodes for Linux at the moment.


Mac
**********************

* If you want use a NAO or Papper robot, then install Python the newest version of 2.7 from: https://www.python.org/downloads/
* Otherwise you can use the anaconda distribution of python 2.7 or the default python instalation.
* Download the most recent version of the NEP social robot programming platform from:
* Open the terminal and run the **install.sh** script

.. warning:: There is not a Kinect V2 and Wii Balance Board comptible nodes for OSX at the moment.


Getting started (Developer)
==================

The NEP plataform is composed by tree main parts, the **core** API, the Google Blocky **interface** and the robot **modules**. 

Core API
**********************

The **core** API contains a set of python methods and classes used to:

* Perform inter-procces comunications using ZeroMQ publish/subcriber pattern. This is done using the **comunication** class.
* Define the human and robot high level social programming primitives, which are used for design social interactions with robots. This is done using the **human** and **robot** class respectively.
* Define the robot control programming primitives.  This is done using the **robot_bahaviors** class.

Interface
**********************

The Google Blocky **interface** provide a visual tool in which novice and expert user can design and program robot social interactions. This is done using the JavaScript based Google Blocky API which generate python code. The generated python code use the **human** and **robot** classes (social primitives) to create and execute the interaction with social robots. 


Modules
**********************

Finally, the robot **modules** contains the hardware and algortihm programming primitives (low level programming asbtraction). There are tree main types of modules:

* **Sensory module:** Gives to the robots the ability of sense the enviroment. This are the input modalities of the robot. Examples are vision (using cameras or kinect), and audio (using kinect).
* **Perceptual module:** Gives to the robots the ability of understand the human actions in based to the sensory information. Exemples are gesture, emotion and speech reconition.
* **Action module:** Gives to the robots the ability of react to the human actions. This are the outputs of the robot. Examples are robot speech, walking, robot gestures, face expresion, among others.

This modules are necesary for the understading of the human actions and the execution of the robot behaviors. However are not directly involved in the design or programming of the robot social interactions. Instead are used or called inside the **human** and **robot** classes to create the high level social primitives. Social, and low level abstraction primitives comunicate togheter using ZeroMQ sockets.

The sensory and perceptual modules can be written in python (Linux, OSX and Windows compatible) or C# (only Windows compatible). 

Robots supported (action module)
**********************

* NAO: using the NAO engine module in modules/action/NAO/nao_action_engine
* Papper (soon)

Sensory devices supported
**********************
* Kinect V2: using the mutimodal sensory WPF interface in ``modules/sensing/csharp/kinect/multimodal``
* Wii Balance Board using the C# program in ``modules/sensing/csharp/wii_balance_board/wiibbtest``
* IMU from Android smartwatches/smartphones: using the python script in ``modules/sensing/python/smartwatch``



Methods and class index
==================
* :ref:`genindex`

Module index
==================

* :ref:`modindex`


