---
UID: NC:trustedruntimeclx.EVT_TR_CREATE_SECURE_SERVICE_CONTEXT
title: EVT_TR_CREATE_SECURE_SERVICE_CONTEXT (trustedruntimeclx.h)
description: 
ms.assetid: b150ac4b-ea12-4acf-8f97-b651f1d59ccb
ms.date: 11/20/2020
keywords: ["EVT_TR_CREATE_SECURE_SERVICE_CONTEXT callback function"]
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
 - EVT_TR_CREATE_SECURE_SERVICE_CONTEXT
 - trustedruntimeclx/EVT_TR_CREATE_SECURE_SERVICE_CONTEXT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - EVT_TR_CREATE_SECURE_SERVICE_CONTEXT
---

# EVT_TR_CREATE_SECURE_SERVICE_CONTEXT callback function

## -description

## -parameters

### -param MasterDevice

### -param ServiceGuid

### -param ServiceDevice

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -syntax

```cpp
//Declaration

EVT_TR_CREATE_SECURE_SERVICE_CONTEXT EvtTrCreateSecureServiceContext;

// Definition

NTSTATUS EvtTrCreateSecureServiceContext
(
    WDFDEVICE MasterDevice
    LPCGUID ServiceGuid
    WDFDEVICE ServiceDevice
)
{...}

```

## -remarks

## -see-also
