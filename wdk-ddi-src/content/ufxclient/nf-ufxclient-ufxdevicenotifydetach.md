---
UID: NF:ufxclient.UfxDeviceNotifyDetach
title: UfxDeviceNotifyDetach function
author: windows-driver-content
description: Notifies UFX that the device's USB cable has been detached.
old-location: buses\ufxdevicenotifydetach.htm
old-project: usbref
ms.assetid: 890C7451-D9BF-4019-ABBE-D97446728E6B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UfxDeviceNotifyDetach
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
req.alt-api: UfxDeviceNotifyDetach
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

# UfxDeviceNotifyDetach function



## -description
Notifies UFX that the device's  USB cable has been detached.



## -syntax

````
VOID UfxDeviceNotifyDetach(
  [in] UFXDEVICE UfxDevice
);
````


## -parameters

### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


## -returns
This method does not return a value.


## -remarks
This method is called by the client driver when it receives a USB cable detach event. Once the detach event is processed, all endpoints should be disabled and device should move to a low power mode.

The client driver typically calls <b>UfxDeviceNotifyDetach</b> from its <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback function, as shown in the following example.</p>