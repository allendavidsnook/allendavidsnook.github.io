---
title: STM32CubeIDE FreeRTOS Include Paths
---

This was odd. I'm noting here so 1) I don't forget and 2) in case anyone else runs into this. My STM32CubeIDE 1.4.0 based project was building fine, I used the STM32CubeMX editor to unlink PC13 from the user button since it was limiting my RTC configuration.



On saving and re-generating, a bunch of my FreeRTOS includes stopped being found by the compiler. Scrutinzing the diff of my .cproject file showed all of the paths had been removed from the configuration.



I added them all back in and the project resumed building normally.



It is possible this is because I've switched to Windows based development for this project, or it is possibly related to the STM32CubeIDE 1.4.2 update, but I am not certain.











Edit: And, this is odd, on a subsequent "save" and "re-generate" the relative include paths that had been deleted were restored.
