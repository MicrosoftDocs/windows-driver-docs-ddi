---
UID: NF:ufxclient.UfxDeviceNotifyFinalExit
title: UfxDeviceNotifyFinalExit function (ufxclient.h)
description: Notifies UFX that the device is detached.
ms.assetid: 7c48f7e0-ce21-40b2-be17-037b70178673
ms.date: 10/19/2018
ms.topic: function
f1_keywords:
 - "ufxclient/UfxDeviceNotifyFinalExit"
ms.keywords: UfxDeviceNotifyFinalExit
req.header: ufxclient.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: ufxstub.lib
req.dll:
req.irql: DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location:
- NtosKrnl.exe
- ufxstub.lib
api_name: 
- UfxDeviceNotifyFinalExit
product:
- Windows
targetos: Windows

---

# UfxDeviceNotifyFinalExit function


## -description

Notifies UFX that the device is detached. 

## -parameters

### -param UfxDevice
A handle to a UFX device object that the driver created by calling [**UfxDeviceCreate**](../ufxclient/nf-ufxclient-ufxdevicecreate.md).

## -remarks

## -see-also
