---
UID: NF:umdprovider.UMDEtwUnregister
title: UMDEtwUnregister function (umdprovider.h)
description: Unregisters the event trace provider. Call this function before the user-mode driver is unloaded. After this function is called, the driver should not make any other calls to log events.
old-location: display\umdetwunregister.htm
tech.root: display
ms.assetid: 19ab8771-2a86-469a-98e4-3d295a458b90
ms.date: 05/10/2018
ms.keywords: UMDEtwUnregister, UMDEtwUnregister function [Display Devices], display.umdetwunregister, umdprovider/UMDEtwUnregister
ms.topic: function
req.header: umdprovider.h
req.include-header: Umdprovider.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- umdprovider.h
api_name:
- UMDEtwUnregister
product:
- Windows
targetos: Windows
req.typenames: 
---

# UMDEtwUnregister function

## -description

Unregisters the event trace provider. Call this function before the user-mode driver is unloaded. After this function is called, the driver should not make any other calls to log events.

## -parameters

## -returns

This function does not return a value.

## -remarks

<b>UMDEtwUnregister</b> is defined inline in Umdprovider.h as:

```cpp
// Registration handle, returned by EventRegister and passed to EventUnregister
__declspec(selectany) REGHANDLE RegHandle = NULL;

FORCEINLINE void UMDEtwUnregister()
{
    EventUnregister(RegHandle);
}
```

The <a href="https://docs.microsoft.com/windows/desktop/api/evntprov/nf-evntprov-eventunregister">EventUnregister</a> function is  described in the <a href="https://docs.microsoft.com/windows/desktop/Events/windows-events">Windows Events</a> documentation.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/umdprovider/nf-umdprovider-umdetwregister">UMDEtwRegister</a>
