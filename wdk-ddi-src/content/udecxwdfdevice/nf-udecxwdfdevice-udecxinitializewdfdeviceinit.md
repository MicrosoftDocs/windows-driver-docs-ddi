---
UID: NF:udecxwdfdevice.UdecxInitializeWdfDeviceInit
title: UdecxInitializeWdfDeviceInit function (udecxwdfdevice.h)
description: Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device.
old-location: buses\udecxinitializewdfdeviceinit.htm
tech.root: usbref
ms.assetid: 6FF62F6B-D83D-45DB-BE83-7A6D61A6AC92
ms.date: 05/07/2018
keywords: ["UdecxInitializeWdfDeviceInit function"]
ms.keywords: UdecxInitializeWdfDeviceInit, UdecxInitializeWdfDeviceInit function [Buses], buses.udecxinitializewdfdeviceinit, udecxwdfdevice/UdecxInitializeWdfDeviceInit
f1_keywords:
 - "udecxwdfdevice/UdecxInitializeWdfDeviceInit"
 - "UdecxInitializeWdfDeviceInit"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Udecxstub.lib
- Udecxstub.dll
api_name:
- UdecxInitializeWdfDeviceInit
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

<p>A pointer to a framework-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure. </p>




## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 




## -remarks



The client driver for the emulated host controller device calls this method in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> implementation before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>. For code example, see <b>UdecxWdfDeviceAddUsbDeviceEmulation</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

