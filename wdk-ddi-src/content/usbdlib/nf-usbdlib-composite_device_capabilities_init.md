---
UID: NF:usbdlib.COMPOSITE_DEVICE_CAPABILITIES_INIT
title: COMPOSITE_DEVICE_CAPABILITIES_INIT function (usbdlib.h)
description: The COMPOSITE_DEVICE_CAPABILITIES_INIT macro initializes the COMPOSITE_DEVICE_CAPABILITIES structure.
old-location: buses\composite_driver_capabilities_init.htm
tech.root: usbref
ms.assetid: 92DDF65E-4B5B-443A-9C90-3B1BB2DD3CAF
ms.date: 05/07/2018
ms.keywords: COMPOSITE_DEVICE_CAPABILITIES_INIT, COMPOSITE_DEVICE_CAPABILITIES_INIT routine [Buses], buses.composite_driver_capabilities_init, usbdlib/COMPOSITE_DEVICE_CAPABILITIES_INIT
ms.topic: function
f1_keywords:
 - "usbdlib/COMPOSITE_DEVICE_CAPABILITIES_INIT"
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbdex.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbdex.lib
- Usbdex.dll
api_name:
- COMPOSITE_DEVICE_CAPABILITIES_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# COMPOSITE_DEVICE_CAPABILITIES_INIT function


## -description


The <b>COMPOSITE_DEVICE_CAPABILITIES_INIT</b> macro initializes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/ns-usbdlib-_composite_device_capabilities">COMPOSITE_DEVICE_CAPABILITIES</a> structure.


## -parameters




### -param CapabilityFlags

 A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/ns-usbdlib-_composite_device_capabilities">COMPOSITE_DEVICE_CAPABILITIES</a> structure to be initialized. The macro sets the <b>CompositeDriverCapabilityFunctionSuspend</b>
member of <b>COMPOSITE_DEVICE_CAPABILITIES</b> to 0.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/ns-usbdlib-_composite_device_capabilities">COMPOSITE_DEVICE_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">How to Register a Composite Device</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/ns-usbdlib-_register_composite_device">REGISTER_COMPOSITE_DEVICE</a>
 

 

