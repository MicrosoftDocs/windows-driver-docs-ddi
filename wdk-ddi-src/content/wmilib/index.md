---
UID: NA:wmilib
author: windows-driver-content
ms.assetid: bca56998-667b-3fd4-9561-ba760c2275b6
ms.author: windowsdriverdev
ms.date: 05/09/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: kernel
---

# Wmilib.h header


## -description


TThis header is used in providing kernel-mode Windows Management Instrumentation (WMI) extensions to WDM. 

Drivers can use these routines in processing WMI IRPs.

- [**WmiCompleteRequest**](nf-wmilib-wmicompleterequest.md) 

- [**WmiSystemControl**](nf-wmilib-wmisystemcontrol.md) 

To handle WMI IRPs by calling WmiSystemControl, a driver must implement certain required callback routines, for information, see [Calling WmiSystemControl to Handle WMI IRPs](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/calling-wmisystemcontrol-to-handle-wmi-irps)


For more information, see:

- [Implementing WMI](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/implementing-wmi)

