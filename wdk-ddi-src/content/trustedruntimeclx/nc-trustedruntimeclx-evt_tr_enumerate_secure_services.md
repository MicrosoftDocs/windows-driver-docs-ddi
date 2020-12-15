---
UID: NC:trustedruntimeclx.EVT_TR_ENUMERATE_SECURE_SERVICES
title: EVT_TR_ENUMERATE_SECURE_SERVICES (trustedruntimeclx.h)
description: 
ms.date: 11/20/2020
keywords: ["EVT_TR_ENUMERATE_SECURE_SERVICES callback function"]
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
 - EVT_TR_ENUMERATE_SECURE_SERVICES
 - trustedruntimeclx/EVT_TR_ENUMERATE_SECURE_SERVICES
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - EVT_TR_ENUMERATE_SECURE_SERVICES
---

# EVT_TR_ENUMERATE_SECURE_SERVICES callback function

## -description

## -parameters

### -param MasterDevice

### -param Index

### -param SecureServiceDescription

### -param DescriptionSize

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -syntax

```cpp
//Declaration

EVT_TR_ENUMERATE_SECURE_SERVICES EvtTrEnumerateSecureServices;

// Definition

NTSTATUS EvtTrEnumerateSecureServices
(
    WDFDEVICE MasterDevice
    ULONG Index
    PUCHAR SecureServiceDescription
    ULONG * DescriptionSize
)
{...}

```

## -remarks

## -see-also
