---
UID: NF:udecxwdfdevice.UdecxWdfDeviceAddUsbDeviceEmulation
title: UdecxWdfDeviceAddUsbDeviceEmulation function (udecxwdfdevice.h)
description: Initializes a framework device object to support operations related to a host controller and a virtual USB device attached to the controller.
old-location: buses\udecxwdfdeviceaddusbdeviceemulation.htm
tech.root: usbref
ms.assetid: EE7644A9-AA57-4C53-9FA5-F844F2BFB0D7
ms.date: 05/07/2018
ms.keywords: UdecxWdfDeviceAddUsbDeviceEmulation, UdecxWdfDeviceAddUsbDeviceEmulation function [Buses], buses.udecxwdfdeviceaddusbdeviceemulation, udecxwdfdevice/UdecxWdfDeviceAddUsbDeviceEmulation
ms.topic: function
req.header: udecxwdfdevice.h
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
-	UdecxWdfDeviceAddUsbDeviceEmulation
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxWdfDeviceAddUsbDeviceEmulation function


## -description


Initializes a framework device object to support operations related to a host controller and a virtual USB device attached to the controller. 


## -parameters




### -param WdfDevice

<p>A handle to the framework device object that the client driver retrieved in the previous call to <a href="https://msdn.microsoft.com/library/Ff545926(v=VS.85).aspx"><b>WdfDeviceCreate</b></a>.</p>


### -param Config [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt628008">UDECX_WDF_DEVICE_CONFIG</a> structure that the client driver initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt628010">UDECX_WDF_DEVICE_CONFIG_INIT</a>.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The UDE client driver for the emulated host controller and the USB device must call this method after the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> call. 

During this call, the client driver-supplied event callback implementations are also registered. Supply function  pointers to those functions by call setting appropriate members of <a href="https://msdn.microsoft.com/library/windows/hardware/mt628008">UDECX_WDF_DEVICE_CONFIG</a>. 

The method makes the framework device object capable of performing operations related to a controller and its root hub, such as handling various queues required to process IOCTL requests sent to the attached USB device. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

