---
UID: NC:trustedruntimeclx.EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT
title: EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT (trustedruntimeclx.h)
description: 
ms.assetid: 398accdf-300c-43d5-b460-f87f83c6edfc
ms.date: 11/20/2020
keywords: ["EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT callback function"]
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
 - EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT
 - trustedruntimeclx/EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT
---

# EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT callback function

## -description

## -parameters

### -param ServiceDevice

### -param SessionContextObject

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -syntax

```cpp
//Declaration

EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT EvtTrCreateSecureServiceSessionContext;

// Definition

NTSTATUS EvtTrCreateSecureServiceSessionContext
(
    WDFDEVICE ServiceDevice
    WDFOBJECT * SessionContextObject
)
{...}

```

## -remarks

## -see-also
