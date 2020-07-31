---
UID: NS:dispmprt._DXGKDDI_FLEXIOV_DEVICE_INTERFACE
title: _DXGKDDI_FLEXIOV_DEVICE_INTERFACE (dispmprt.h)
description: 
ms.assetid: 03ceba62-6439-4a5e-b15b-38dd06a6a924
ms.date: 10/19/2018
keywords: ["_DXGKDDI_FLEXIOV_DEVICE_INTERFACE structure"]
f1_keywords:
 - "dispmprt/_DXGKDDI_FLEXIOV_DEVICE_INTERFACE"
 - "_DXGKDDI_FLEXIOV_DEVICE_INTERFACE"
ms.keywords: _DXGKDDI_FLEXIOV_DEVICE_INTERFACE, DXGKDDI_FLEXIOV_DEVICE_INTERFACE, *PDXGKDDI_FLEXIOV_DEVICE_INTERFACE, 
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKDDI_FLEXIOV_DEVICE_INTERFACE, *PDXGKDDI_FLEXIOV_DEVICE_INTERFACE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- dispmprt.h
api_name: 
- _DXGKDDI_FLEXIOV_DEVICE_INTERFACE
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# _DXGKDDI_FLEXIOV_DEVICE_INTERFACE structure

## -description

Describes the Flexible IOV (input/output virtualization) kernel mode driver interface.

## -struct-fields

### -field Size

The size of the structure.

### -field Version

Interface version.

### -field Context

Context to associate with the interface.

### -field InterfaceReference

Interface reference function to be called when adding references.

### -field InterfaceDereference

Interface reference function to be called when deallocating references.

### -field DxgkDdiGetBackingResource

Points to a get backing resource function.

### -field DxgkDdiGetMmioRangeCount

Points to a get memory range count function.

### -field DxgkDdiGetMmioRanges
 
Points to a get memory range function.

## -remarks

## -see-also
