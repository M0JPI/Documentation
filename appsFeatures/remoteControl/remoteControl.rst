.. _remoteControl:

SCPI server (MATLAB, LabVIEW, Scilab or Python)
##################################################

.. https://owncloud.redpitaya.com/index.php/apps/files/?dir=%2FWEB%20page%2Fapps%2FSCPI

.. figure:: SCPI_web_lr.png

Red Pitaya board can be controlled remotely over LAN or wireless interface
using MATLAB, LabVIEW, Scilab or Python via Red Pitaya
SCPI (Standard Commands for Programmable Instrumentation) list of commands.
SCPI interface/environment is commonly used to control T&M instruments
for development, research or test automation purposes.
SCPI uses a set of SCPI commands that are recognized by the instruments
to enable specific actions to be taken
(e.g.: acquiring data from fast analog inputs, generating signals and
controlling other periphery of the Red Pitaya platform).
The SCPI commands are extremely useful when complex signal analysis
is required where SW environment such as MATLAB provides powerful data analysis tools
and SCPI commands simple access to raw data acquired on Red Pitaya board.

**Features**

- Quickly write control routines and programs using  MATLAB, LabVIEW, Scilab or Python
- Use powerful data analysis tools of MATLAB, LabVIEW, Scilab or Python to analyze raw signals
  acquired by Red Pitaya board
- Write testing scripts and routines
- Incorporate your Red Pitaya and LabVIEW  into testing and production lines
- Take quick measurements directly with your PC

***********
Quick start
***********

Start SCPI server, this is done simply by clicking the SCPI server icon and starting the SCPI server.
When SCPI server is started the IP of your board will be shown.
This IP you need to input in to your scripts.
Starting SCPI server can be also done manually via Terminal(check bellow).

To run an examples follow instructions bellow:

#. Go to your Red Pitaya main page and Select SCPI server.

   .. figure:: scpi-homepage.png

   .. figure:: scpi-development.png

#. Start SCPI server by selecting RUN button.
   Please notice the IP of your Red Pitaya (192.168.178.100) board as it will be needed to connect to your board.

   .. figure:: scpi-app-run.png

   .. figure:: scpi-app-stop.png

#. Follow the instructions bellow sutable to your environment.

   .. note::

      It is not possible to run SCPI commands/programs in parallel with web applications.

.. contents::
    :local:
    :backlinks: none
    :depth: 1

======
MATLAB
======

#. Open MATLAB on your computer
#. Copy the Code from :ref:`blink <blink>` tutorial example to MATLAB workspace
#. Replace the IP in the example with the IP of your Red Pitaya board
#. Hit RUN or F5 on your keyboard to run the code

More examples about how to control Red Pitaya from MATLAB can be find :ref:`here <examples>`.

======
Python
======

The `PyVISA <http://pyvisa.readthedocs.io/en/stable/index.html>`_ library in combination with
the `PyVISA-py <http://pyvisa-py.readthedocs.io/en/latest/>`_ backend are used.
To install them do:

   .. code-block:: shell-session

      $ sudo pip3 install pyvisa pyvisa-py

   .. note::

         To run the examples, you need Python version 3. Make sure the Python versions before running.
         If the system has Python version 2.7, this version will be used by default.

         .. code-block:: shell-session

            $ python --version
            Python 2.7.17
         
         Then, in order to run the examples, specify explicitly the Python version

         .. code-block:: shell-session

            $ python3.5 blink.py 192.168.178.108

#. Open the :ref:`blink <blink>` tutorial and copy the code to your favorite text editor
#. Save the file as ``blink.py`` to your working folder → for example ``examples_py``
#. Copy and save the
   `redpitaya_scpi.py <https://github.com/RedPitaya/RedPitaya/blob/master/Examples/python/redpitaya_scpi.py>`_
   `` script in to the same folder where you have saved ``blink.py`` example (in our case
   it will be ``examples_py``).

   .. note::

      ``redpitaya_scpi.py`` script is a standard script needed to
      establish the connection between your PC and Red Pitaya board.
      Without having this script in the same folder as your Python script
      the execution of your script will fail.

   .. figure:: scpi-examples.png

#. Open the Terminal and go to the folder containing your Python script
   (``examples_py``) and run: ``Python blink.py IP`` where you give an Red Pitaya IP
   as the argument when calling an execution of the ``blink.py`` example.
   Example is given bellow where ``192.168.178.108`` is the IP of the Red Pitaya board.

   .. code-block:: shell-session

      cd /home/zumy/Desktop/exmples_py
      python blink.py 192.168.178.108

   .. figure:: scpi-example-cli.png

More examples about how to control Red Pitaya from MATLAB can be find :ref:`here <examples>`.

   .. note::
   
      Python examples can also be run directly from RP device itself. To do so fist start SCPI server and then use local device IP: 127.0.0.1

=======
LabVIEW
=======

To set up the LabVIEW driver for Red Pitaya,
download the
`Red_Pitaya_LabVIEW_Driver&Examples.zip <https://downloads.redpitaya.com/downloads/Clients/labview/Red_Pitaya_LabVIEW_Driver%26Examples.zip>`_ file.
Unpack it and copy the Red Pitaya folder to your LabVIEW installations ``instr.lib`` folder
e.g. ``C:/Program Files/National Instruments/LabVIEW 2010/instr.lib``. When using the 64-bit LabVIEW version (mostly
paid). Or here : ``C:/Program Files (x86)/National Instruments/LabVIEW 2020/instr.lib``
when using the 32-bit LabVIEW version, like the free Community Edition.

The Red Pitaya driver should appear after restarting LabVIEW in
Block Diagram -> Instrument I/O -> Instr Drivers -> RedPitaya.
Depending on your settings Instrument I/O may be hidden.
Please consult LabVIEW Help on how to activate/deactivate those categories.
You can access example VIs by going to:

#. Help -> Find Examples...
#. click Search tab
#. Enter **RedPitaya** in Enter keyword(s) field

More examples about how to control Red Pitaya from LabVIEW can be found :ref:`here <examples>`.

======
SCILAB
======

To use the SCPI commands you will need to set up Scilab sockets. The procedure is described below.

#. Go to `Scilab download page <http://www.scilab.org/download/>`_ and download and Install Scilab for your OS
#. Go to `Scilab socket toolbox page <https://atoms.scilab.org/toolboxes/socket_toolbox>`_ and download the basic socket function for Scilab.
#. Go to the extracted Scilab folder then to folder named ``contrib``
#. Copy socket_toolbox zip file to contrib folder
#. Extract socket_toolbox zip file inside the contrib folder
#. Delete socket_toolbox zip file because we dont need it any more
#. Go to socket_toolbox folder
#. Open loader.sce with your Scilab and press RUN (grey run button on SCILAB editor gui)

These last two steps must be executed each time you start Scilab.
To install installing you must have an internet connection.
Running the examples is same as on MATALB

#. Copy the Code from :ref:`blink <blink>` tutorial example to MATLAB workspace
#. Replace the IP in the example with the IP of your Red Pitaya board
#. Press  RUN to run the code

Different code examples can be found on the `Examples page <http://redpitaya.com/examples-new/>`_.

.. note::

   Communicating with scpi server and working with web based instruments
   at the same time can diminish the performance of your Red Pitaya.
   This is because the same resource is used for both tasks.

More examples about how to control Red Pitaya from MATLAB can be find :ref:`here <examples>`.

*****************************
Starting SCPI server manually
*****************************

Assuming you have successfully connected to your Red Pitaya board using :ref:`these<faqConnected>` instructions.
Remotely connect using Putty on Windows machines or
with :ref:`SSH <ssh>` using Terminal on UNIX (macOSX/Linux) machines.

Connect to your Red Pitaya board via terminal on a Linux machine
and start SCPI server with the following command:

.. code-block:: shell-session

   systemctl start redpitaya_scpi &

.. figure:: scpi-ssh.png

.. _scpiCommand:

.. include:: SCPI_commands.rst

.. _examples:

********
Examples
********

In the list bellow you will find examples of remote control and C algorithms. This examples are covering all
basic Red Pitaya functionalities such as:

    - signal generation
    - signal acquisition
    - digital I/O control
    - communication protocols

You can edit and change them according to your needs and develop customized programs and routines.

.. toctree::
   :maxdepth: 2


   ../examples/digital
   ../examples/analog
   ../examples/genRF
   ../examples/acqRF
   ../examples/digcomIF

Additional examples: :ref:`ABCLED`
