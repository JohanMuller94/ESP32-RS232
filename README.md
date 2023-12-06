# ESP32-RS232
Captive portal for configuring an easy RS232 communication device, to integrate with HA through ESPHome.
This project is made with projector control in mind.

Remember to correct UART settings like baud rate. Look up the documentation of the device to make sure there is a match.
Commonly used is the current setting of this file. You might be lucky that it works.

This ESPHome config creates two switches,5 text inputs where you can input commands to control projectors and one sensor.

1. Power (Switches device On/Off. If feedback is enabled with correct commands, the switch will allign with current state of controlled device.)
2. Feedback (Like explained above - This switch enables an interval, sending the Feedback Command every 10 second.)
3. Power On (Command to turn projector on)
4. Power Off (Command to turn projector off)
5. Feedback (Command asking the on/off state of the projector)
6. Answer On (Reply from device if On)
7. Answer Off (Reply from device if Off)

After inputting these 5 commands, you can press:
8. Save Commands - This will store the commands to the memory of the device, saving them in case of a powercycle.

After a powercycle of the device, the unit should self populate the text fields with latest commands stored.
In case not, use the button:
9. Update Text Fields

There is a sensor comparing the stored commands to the ones present in the text fields.
In case you are updating the text fields, the sensor will write "Update available", indicating that there is unsaved commands.

