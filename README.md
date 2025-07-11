# DS1054Z_data_logger

This script is modified to run in a python3 environment.
With python3.13 there is no telnetlib bundled any more. It is necessary to install telnetlib-313-and-up (https://pypi.org/project/telnetlib-313-and-up/).

'**DS1054Z_logger.py**' is a Python script that adds frequency measurement for all the 4 (i used 2 channels, so 3 and 4 are commented out) channels of a Rigol DHO804/DHO924 (will work with other LXI scopes, too) oscilloscope, then periodically log the freq values in a PC file using a LAN connexion between computer and oscilloscope. No drivers are required to be installed on the PC.

<pre># Print usage
def print_help():
    print
    print ("This program periodically reads the frequency measured")
    print ("    for all 2(4) channels of a Rigol DHO804/DHO924 oscilloscope.")
    print
    print ("    The reading time interval (in seconds) can be specified")
    print ("    in the command line. A timestamp is added for each new reading.")
    print
    print ("    At each new reading, the freq values for each channel")
    print ("    are listed in CSV format, then saved in a log file. The log file")
    print ('    is saved as "MODEL_YYYY-MM-DD_HH.MM.SS.csv"')
    print
    print ("The program is using LXI protocol, so the computer")
    print ("    must have LAN connection with the Rigol instrument.")
    print ("    USB and/or GPIB connections are not used by this software.")
    print
    print ("    No VISA, IVI or Rigol drivers are needed.")
    print
    print ("Usage syntax:")
    print ("    " + "python " + scriptName + " [read_interval [instrument_IP]]")
    print
    print ("Usage examples:")
    print ("    " + "python " + scriptName + "                   # log outputs (0.5s, 192.168.1.3)")
    print ("    " + "python " + scriptName + " 60                # log at each minute (192.168.1.3)")
    print ("    " + "python " + scriptName + " 3600 192.168.1.7  # log hourly from IP 192.168.1.7")
    print
    print ("To end the logging, press 'ESC'.")
    print
    print
    print
</pre>
