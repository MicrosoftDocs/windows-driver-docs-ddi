---
UID: NF:udecxusbdevice.UdecxUsbDeviceSignalWake
title: UdecxUsbDeviceSignalWake function
description: Initiates wake up from a low link power state for a virtual USB 2.0 device.
old-location: buses\udecxusbdevicesignalwake.htm
tech.root: usbref
ms.assetid: BF8C1D85-6C88-4F4C-ADDB-CCE603D420F2
ms.date: 05/07/2018
ms.keywords: UdecxUsbDeviceSignalWake, UdecxUsbDeviceSignalWake function [Buses], buses.udecxusbdevicesignalwake, udecxusbdevice/UdecxUsbDeviceSignalWake
ms.topic: function
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUsbDeviceSignalWake
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceSignalWake function


## -description


Initiates wake up from a low link power state for a virtual USB 2.0 device.



## -parameters




### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.


## -returns



This function does not return a value.




## -remarks



The client driver for the device must have enabled wake capability in the most recent <a href="https://msdn.microsoft.com/library/windows/hardware/mt595911">EVT_UDECX_USB_DEVICE_D0_EXIT</a> call.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595911">EVT_UDECX_USB_DEVICE_D0_EXIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

