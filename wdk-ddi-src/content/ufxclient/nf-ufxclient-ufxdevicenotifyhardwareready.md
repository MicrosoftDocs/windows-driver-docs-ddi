---
UID: NF:ufxclient.UfxDeviceNotifyHardwareReady
title: UfxDeviceNotifyHardwareReady function
author: windows-driver-content
description: Notifies UFX that the hardware is ready.
old-location: buses\ufxdevicenotifyhardwareready.htm
old-project: usbref
ms.assetid: B4BE0BDC-C1A3-4230-8F4B-78DE34F5554D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UfxDeviceNotifyHardwareReady
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UfxDeviceNotifyHardwareReady
req.alt-loc: ufxclient.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxDeviceNotifyHardwareReady function



## -description
Notifies UFX that the hardware is ready.



## -syntax

````
VOID UfxDeviceNotifyHardwareReady(
  [in] UFXDEVICE UfxDevice
);
````


## -parameters

### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


## -returns
This method does not return a value.


## -remarks
The client driver typically calls <b>UfxDeviceNotifyHardwareReady</b> from its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> callback function, as shown in the following example.</p>