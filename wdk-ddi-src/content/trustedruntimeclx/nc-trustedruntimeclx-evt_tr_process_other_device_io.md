---
UID: NC:trustedruntimeclx.EVT_TR_PROCESS_OTHER_DEVICE_IO
title: EVT_TR_PROCESS_OTHER_DEVICE_IO (trustedruntimeclx.h)
description: "Learn more about: EVT_TR_PROCESS_OTHER_DEVICE_IO callback function"
ms.date: 11/20/2020
keywords: ["EVT_TR_PROCESS_OTHER_DEVICE_IO callback function"]
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
 - EVT_TR_PROCESS_OTHER_DEVICE_IO
 - trustedruntimeclx/EVT_TR_PROCESS_OTHER_DEVICE_IO
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - EVT_TR_PROCESS_OTHER_DEVICE_IO
---

# EVT_TR_PROCESS_OTHER_DEVICE_IO callback function

## -description

## -parameters

### -param MasterDevice

### -param Request

## -syntax

```cpp
//Declaration

EVT_TR_PROCESS_OTHER_DEVICE_IO EvtTrProcessOtherDeviceIo;

// Definition

VOID EvtTrProcessOtherDeviceIo
(
    WDFDEVICE MasterDevice
    WDFREQUEST Request
)
{...}

```

## -remarks

## -see-also
