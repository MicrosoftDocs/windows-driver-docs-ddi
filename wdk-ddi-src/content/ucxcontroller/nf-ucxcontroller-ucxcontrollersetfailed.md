---
UID: NF:ucxcontroller.UcxControllerSetFailed
title: UcxControllerSetFailed function (ucxcontroller.h)
description: Informs USB Host Controller Extension (UCX) that the controller has encountered a critical failure.
old-location: buses\_ucxcontrollersetfailed.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UcxControllerSetFailed function"]
ms.keywords: UcxControllerSetFailed, UcxControllerSetFailed method [Buses], buses._ucxcontrollersetfailed, ucxcontroller/UcxControllerSetFailed
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UcxControllerSetFailed
 - ucxcontroller/UcxControllerSetFailed
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Ucxcontroller.h
api_name:
 - UcxControllerSetFailed
---

# UcxControllerSetFailed function


## -description

Informs USB Host Controller Extension (UCX) that the controller has encountered a critical failure.

## -parameters

### -param Controller [in]


A handle to the controller object. The client driver retrieved the handle in a previous call to <a href="/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a>.

## -remarks

    The client driver for host controller must call this function if the driver fails D0 entry or the driver has stopped processing transfers to or from an endpoint.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a>
