---
UID: NC:trustedruntimeclx.PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL
title: PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL (trustedruntimeclx.h)
description: 
ms.date: 11/20/2020
keywords: ["PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL callback function"]
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
 - PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL
 - trustedruntimeclx/PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL
---

# PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL callback function

## -description

## -parameters

### -param BindContextObject

### -param DeviceInit

### -param ServiceGuid

### -param Callbacks

### -param ServiceDevice

## -returns

Returns WDFAPI

## -syntax

```cpp
//Declaration

PFN_TRSECUREDEVICEHANDOFFSERVICEDEVICECONTROL PfnTrsecuredevicehandoffservicedevicecontrol;

// Definition

WDFAPI PfnTrsecuredevicehandoffservicedevicecontrol
(
    WDFOBJECT BindContextObject
    PWDFDEVICE_INIT DeviceInit
    LPGUID ServiceGuid
    PTR_SECURE_SERVICE_CALLBACKS Callbacks
    WDFDEVICE *ServiceDevice
)
{...}

```

## -remarks

## -see-also
