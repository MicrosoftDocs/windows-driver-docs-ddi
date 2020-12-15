---
UID: NC:trustedruntimeclx.EVT_TR_QUERY_SERVICE_CALLBACKS
title: EVT_TR_QUERY_SERVICE_CALLBACKS (trustedruntimeclx.h)
description: 
ms.date: 11/20/2020
keywords: ["EVT_TR_QUERY_SERVICE_CALLBACKS callback function"]
req.header: trustedruntimeclx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
tech.root: treedrv
f1_keywords:
 - EVT_TR_QUERY_SERVICE_CALLBACKS
 - trustedruntimeclx/EVT_TR_QUERY_SERVICE_CALLBACKS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - EVT_TR_QUERY_SERVICE_CALLBACKS
---

# EVT_TR_QUERY_SERVICE_CALLBACKS callback function

## -description

## -parameters

### -param MasterDevice

### -param ServiceGuid

## -returns

Returns PTR_SECURE_SERVICE_CALLBACKS.

## -syntax

```cpp
//Declaration

EVT_TR_QUERY_SERVICE_CALLBACKS EvtTrQueryServiceCallbacks;

// Definition

PTR_SECURE_SERVICE_CALLBACKS EvtTrQueryServiceCallbacks
(
    WDFDEVICE MasterDevice
    LPGUID ServiceGuid
)
{...}

```

## -remarks

## -see-also
