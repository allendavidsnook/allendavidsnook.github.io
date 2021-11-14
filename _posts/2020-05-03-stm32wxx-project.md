---
title: STM32WXX Project
---

I've been working on a ARM Cortex M4 based weather station with APRS transmitter as part of my Masters in Electrical Engineering at the University of Washington. I'm making good progress. It is FreeRTOS based and I've gotten all the tasks and queues running and time, location, and weather data flowing. I integrated with the real time clock just to find out that it drifts 5 minutes per hour - looks like I'll need to periodically re-synchronize that with the GPS signal, LOL.



This is a complete rebuild of the Texas Instruments Tiva based project with a better&nbsp; sensor for weather and an MCU from the much more popular STM32 family.



Next step is to write an AX.25 packetizer and the modulator. You can follow my progress here or on GitHub: https://github.com/allendav/STM32WXX
