---
UID: TP:gpio
title: General-Purpose I/O (GPIO)
ms.assetid: 808f4f69-8260-3b04-a82f-08c14310daa7
ms.date: 05/09/2018
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
product:
- Windows
---

# General-Purpose I/O (GPIO)

## -description

The general-purpose I/O (GPIO) controller driver communicates with the GPIO framework extension (GpioClx) through the GpioClx device-driver interface (DDI). This DDI is defined in the Gpioclx.h header file and is described in this section. As part of this DDI, GpioClx implements several driver support methods, which are called by the GPIO controller driver. This driver implements a set of event callback functions, which are called by GpioClx. GpioClx uses these callbacks to manage interrupt requests from GPIO pins that are configured as interrupt inputs, and to transfer data to or from GPIO pins that are configured as data inputs and outputs.

For conceptual information about writing GPIOClx client drivers, see [General-Purpose I/O (GPIO) Driver Design Guide](https://docs.microsoft.com/windows-hardware/drivers/gpio)


