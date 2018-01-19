---
UID: NF:ufxclient.UfxDeviceIoInternalControl
title: UfxDeviceIoInternalControl function
author: windows-driver-content
description: Passes kernel mode IOCTLs to UFX.
old-location: buses\ufxdeviceiointernalcontrol.htm
old-project: usbref
ms.assetid: 0AD4316E-67E7-4810-86DA-5DEB5C4E6DE6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UfxDeviceIoInternalControl
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
req.alt-api: UfxDeviceIoInternalControl
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

# UfxDeviceIoInternalControl function



## -description
Passes kernel mode IOCTLs to UFX.



## -syntax

````
BOOLEAN UfxDeviceIoInternalControl(
  [in] UFXDEVICE  UfxDevice,
  [in] WDFREQUEST Request,
  [in] size_t     OutputBufferLength,
  [in] size_t     InputBufferLength,
  [in] ULONG      IoControlCode
);
````


## -parameters

### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


### -param Request [in]

A handle to a framework request object.


### -param OutputBufferLength [in]

The length, in bytes, of the request's output buffer, if an output buffer is available.


### -param InputBufferLength [in]

The length, in bytes, of the request's input buffer, if an input buffer is available.


### -param IoControlCode [in]

The driver-defined or system-defined IOCTL that is associated with the request.


## -remarks
The client driver calls <b>UfxDeviceIoInternalControl</b> to forward internal IOCTLs that it receives in its <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_internal_device_control.md">EvtIoInternalDeviceControl</a> callback function to UFX.  The following example shows how:</p>