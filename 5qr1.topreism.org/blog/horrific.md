hack for serial mice on xenocara
================================

disclaimer: im not an expert :- ( please email me if anything here is wrong and/or if theres a better/non hacky way to do this

xenocara limits itself to only be able to access certain files. `/dev/cuaU0` is not one of those files, so it's impossible to use a serial mouse mounted at /dev/cuaU0, right? wrong! delete `/dev/wsmouse` and symlink `/dev/cuaU0` to it, and point your xorg.conf there. its disgusting but works :- )

`Section "ServerFlags"
	Option "AutoAddDevices" "Off"
EndSection

Section "InputDevice"
	Identifier "SerialMouse"
	Driver "mouse"
	Option "Protocol" "Microsoft"
	Option "Baudrate" "1200"
	Option "Device" "/dev/wsmouse"
EndSection
`
