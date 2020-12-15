---
UID: NF:poscx.PosCxCleanPendingRequests
title: PosCxCleanPendingRequests function (poscx.h)
description: PosCxCleanPendingRequests is called to cancel all pending requests for a given caller, identified by the open instance.
old-location: pos\poscxcleanpendingrequests.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["PosCxCleanPendingRequests function"]
ms.keywords: PosCxCleanPendingRequests, PosCxCleanPendingRequests function, pos.poscxcleanpendingrequests, poscx/PosCxCleanPendingRequests
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
f1_keywords:
 - PosCxCleanPendingRequests
 - poscx/PosCxCleanPendingRequests
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxCleanPendingRequests
---

# PosCxCleanPendingRequests function


## -description

PosCxCleanPendingRequests is called to cancel all pending requests for a given caller, identified by the open instance.

## -parameters

### -param device 

[in]
A handle to a framework device object that represents the device.

### -param callerFileObj 

[in, optional]
A handle to a framework file object for which all pending requests should be cancelled, or NULL to cancel all pending requests.

### -param completionStatus 

[in]
An appropriate NTSTATUS error code that indicates success or failure.

