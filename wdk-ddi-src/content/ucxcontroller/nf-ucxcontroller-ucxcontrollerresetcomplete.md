---
UID: NF:ucxcontroller.UcxControllerResetComplete
title: UcxControllerResetComplete function (ucxcontroller.h)
description: Informs USB Host Controller Extension (UCX) that the reset operation has competed.
old-location: buses\_ucxcontrollerresetcomplete.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UcxControllerResetComplete function"]
ms.keywords: UcxControllerResetComplete, UcxControllerResetComplete method [Buses], buses._ucxcontrollerresetcomplete, ucxcontroller/UcxControllerResetComplete
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UcxControllerResetComplete
 - ucxcontroller/UcxControllerResetComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Ucxcontroller.h
api_name:
 - UcxControllerResetComplete
---

# UcxControllerResetComplete function


## -description

Informs USB Host Controller Extension (UCX) that the reset operation has competed.

## -parameters

### -param Controller 

[in]
A handle to the controller object to reset. The client driver retrieved the handle in a previous call to <a href="/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a>.

### -param UcxControllerResetCompleteInfo

TBD

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>
