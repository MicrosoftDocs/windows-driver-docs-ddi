---
UID: NF:ufxclient.UfxDeviceEventComplete
title: UfxDeviceEventComplete function
author: windows-driver-content
description: Informs UFX that the client driver has completed processing a UFX callback function.
old-location: buses\ufxdeviceeventcomplete.htm
old-project: usbref
ms.assetid: DAC18721-5747-4D5E-8A25-24B80DE77C99
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UfxDeviceEventComplete
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
req.alt-api: UfxDeviceEventComplete
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

# UfxDeviceEventComplete function



## -description
Informs UFX that the client driver has completed processing a UFX callback function.



## -syntax

````
VOID UfxDeviceEventComplete(
  [in] UFXDEVICE UfxDevice,
  [in] NTSTATUS  Status
);
````


## -parameters

### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


### -param Status [in]

Status of the event being completed.


## -returns
This method does not return a value.


## -remarks
The client driver calls <b>UfxDeviceEventComplete</b> to signal completion of the following callback functions:

For example, your callback function could use the following code:</p>