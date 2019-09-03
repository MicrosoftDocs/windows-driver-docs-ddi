---
UID: NS:dispmprt._DXGKARG_SETVIRTUALFUNCTIONPOWERSTATE
title: _DXGKARG_SETVIRTUALFUNCTIONPOWERSTATE
author: windows-driver-content
description: Used to set virtual function power state.
tech.root: display
ms.assetid: 9dfe1c32-54a4-41d9-85b7-89872c807359
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: struct
f1_keywords:
 - "dispmprt/_DXGKARG_SETVIRTUALFUNCTIONPOWERSTATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_SETVIRTUALFUNCTIONPOWERSTATE, DXGKARG_SETVIRTUALFUNCTIONPOWERSTATE, *PDXGKARG_SETVIRTUALFUNCTIONPOWERSTATE, 
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: 
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARG_SETVIRTUALFUNCTIONPOWERSTATE, *PDXGKARG_SETVIRTUALFUNCTIONPOWERSTATE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGKARG_SETVIRTUALFUNCTIONPOWERSTATE
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGKARG_SETVIRTUALFUNCTIONPOWERSTATE structure

## -description

Used to set virtual function power state.

## -struct-fields

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field PowerState

New power state for the device.  See the definition of DEVICE_POWER_STATE for more information.

### -field Wake
 
Boolean value indicating whether the device should have its wake signal (PME for PCI Express devices) armed as it goes into the low power state.  This value will be FALSE if PowerState is PowerDeviceD0.

## -remarks

## -see-also
