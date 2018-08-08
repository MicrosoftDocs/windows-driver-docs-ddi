---
UID: NF:udecxwdfdevice.UdecxInitializeWdfDeviceInit
title: UdecxInitializeWdfDeviceInit function
author: windows-driver-content
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\udecxinitializewdfdeviceinit.htm
tech.root: usbref
ms.assetid: 6FF62F6B-D83D-45DB-BE83-7A6D61A6AC92
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: UdecxInitializeWdfDeviceInit, UdecxInitializeWdfDeviceInit function [Buses], buses.udecxinitializewdfdeviceinit, udecxwdfdevice/UdecxInitializeWdfDeviceInit
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	UdecxInitializeWdfDeviceInit
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxInitializeWdfDeviceInit function


## -description


Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.


## -parameters




### -param WdfDeviceInit

TBD




#### - DeviceInit

A pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure. 


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The client driver for the emulated host controller device calls this method in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> implementation before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/mt627990">UdecxWdfDeviceAddUsbDeviceEmulation</a>. For code example, see <b>UdecxWdfDeviceAddUsbDeviceEmulation</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

