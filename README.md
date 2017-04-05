# wakaama-mbed
connecting a lpc1768 to leshan server using lwm2m protocol
<span class="images">![](https://github.com/mohesk/wakaama-mbed/blob/master/PastedGraphic-1-1.tiff)</span>
# Compile and try it
To compile it you need the [ARM GNU toolschains](https://launchpad.net/gcc-arm-embedded), 
GCC ARM Embedded can be installed freely using instructions found [here](http://gnuarmeclipse.livius.net/blog/toolchain-install/).

Then run the classic :
```
make
```
by default the device will try to connect to the [leshan](https://github.com/eclipse/leshan) [sandbox](http://leshan.eclipse.org/#/clients) with the client endpont name `lcp1768`
You could change the endpoint name and the server target with `make` variables :
```
make clean
make ENDPOINT_NAME=mydevice SERVER_URI=coap://10.0.0.1:5683
```

To compile in debug mode and get some logs on [serial port](https://developer.mbed.org/handbook/SerialPC#host-interface-and-terminal-application) : 
```
make clean
make DEBUG=1
```

You could also change ethernet timeout for each loop with `LOOP_TIMEOUT`, the default is 1000ms :
```
make clean
make LOOP_TIMEOUT=200
```
