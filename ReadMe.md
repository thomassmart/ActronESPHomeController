# ESPHome Actron Web Controller 🆒
# This is a work in progress, and only bench tested

## 1. Why? 🤔
I am privilieged enough to have a ducted air conditioning in my home. These systems differ from 'split' system or wall/window mounted units as they are built into the house. They typically have a number of components, mainly:
1. Indoor Unit - Which contains some electronics, and cools recirculated air
1. Controller - Typically not smart, some may have a 7 day timer, and new models may have wifi
1. Outdoor Unit - which compresses the gas
1. Zones - Baffles in the ducting that can control airflow to rooms/areas in the house

Air conditioning, like most climate control options, consumes a large amount of electricity. The age and simplicity from my system does not lend itself to an efficient solution based on presence, or time of day requirements. Welcome back to 2011 and enter the Nest Thermostat. Unfortunately the Nest Thermostat does not work with my system, and in order to replace the controller, both the indoor and outdoor unit would need to be replaced. This is cost inhibitive. This project seeks to hack the existing controller, it's push buttons and LED indicators to bring a little modern intelligence to the system

## 2. How? 🔌
The main components at play here are:
1. Home Assistant
2. ESP Home Software
3. ESP32 Development Board
4. Actron Air LM7 Controller

The ESPHome will be hardwired to the existing LM7 controller, one GPIO pin to the momentary push button, and another to the LED indicator.

The surfaced switch reads the LED to determine the switch state. Should the alternate state be desired, ESPHome momentarily presses the button. Thing of this solution as a halfway between a Nest Thermostat and a Switchbot.