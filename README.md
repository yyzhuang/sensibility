Sensibility Testbed repo
======

To use the sensor code:

1. import necessary library:
  dy_import_module_symbols("sensorutil")
  dy_import_module_symbols("android")

2. set up connection to sl4a:
  sl4a_socket = openconnection("127.0.0.1", ap_port, "127.0.0.1", 12345, 5)

3. use the above socket to get sensor values:
  result = android_get_environment(sl4a_socket)
  log(result + '\n\n')

4. ./adb push test_sensors.repy path/to/repyv2 (e.g., /sdcard/sl4a/seattle/seattle_repyv2)

5. cd /data/local/tmp
   . ./exports.sh

6. cd path/to/repyv2
   python repy.py restriction_file dylink.repy test_sensors.repy 45678
   here the port number 45678 is the local port sl4a is listening on (see exports.sh for value)
