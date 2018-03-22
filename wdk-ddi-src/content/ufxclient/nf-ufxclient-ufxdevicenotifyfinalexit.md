---
UID: NF:ufxclient.UfxDeviceNotifyFinalExit
title: UfxDeviceNotifyFinalExit function
author: windows-driver-content
description: TBD
ms.assetid: 7c48f7e0-ce21-40b2-be17-037b70178673
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
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
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
-   ufxstub.lib
apiname: 
-	UfxDeviceNotifyFinalExit
product: Windows
targetos: Windows

---

# UfxDeviceNotifyFinalExit function


## -description

Notifies UFX that the device is detached. 

## -parameters

### -param UfxDevice
A handle to a UFX device object that the driver created by calling [**UfxDeviceCreate**](..\ufxclient\nf-ufxclient-ufxdevicecreate.md).

## -returns
This function returns VOID.
## -remarks

## -see-also