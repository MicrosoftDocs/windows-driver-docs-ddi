---
UID: NS:dispmprt._DXGKARG_GETVENDORANDDEVICE
title: _DXGKARG_GETVENDORANDDEVICE
description: Arguments used to supply the Vendor and Device IDs for a PCI Express SR-IOV Virtual Function (VF) to be used as the basis for the more generic Plug and Play IDs for the VF.
tech.root: display
ms.assetid: bbe8ab64-b48d-44f6-b79b-6b90d3b33c1f
ms.date: 04/04/2019
keywords: ["DXGKARG_GETVENDORANDDEVICE structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_GETVENDORANDDEVICE, DXGKARG_GETVENDORANDDEVICE, *PDXGKARG_GETVENDORANDDEVICE,
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
req.typenames: DXGKARG_GETVENDORANDDEVICE, *PDXGKARG_GETVENDORANDDEVICE
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKARG_GETVENDORANDDEVICE
 - dispmprt/_DXGKARG_GETVENDORANDDEVICE
 - PDXGKARG_GETVENDORANDDEVICE
 - dispmprt/PDXGKARG_GETVENDORANDDEVICE
 - DXGKARG_GETVENDORANDDEVICE
 - dispmprt/DXGKARG_GETVENDORANDDEVICE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_GETVENDORANDDEVICE
product:
 - Windows
dev_langs:
 - c++
---

# _DXGKARG_GETVENDORANDDEVICE structure


## -description

Arguments used to supply the Vendor and Device IDs for a PCI Express SR-IOV Virtual Function (VF) to be used as the basis for the more generic Plug and Play IDs for the VF.

## -struct-fields

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field VendorId

To be filled in with the Vendor ID to be used for this function.

### -field DeviceId

 
To be filled in with the Device ID to be used for this function.

## -remarks

## -see-also

