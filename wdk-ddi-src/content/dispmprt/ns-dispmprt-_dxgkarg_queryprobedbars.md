---
UID: NS:dispmprt._DXGKARG_QUERYPROBEDBARS
title: _DXGKARG_QUERYPROBEDBARS
author: windows-driver-content
description: Query probed base address registers (BARS).
tech.root: display
ms.assetid: 5f7eb745-1ff6-4c6c-9935-7d85e754459c
ms.author: windowsdriverdev
ms.date: 04/04/2019 
keywords: ["_DXGKARG_QUERYPROBEDBARS structure"]
f1_keywords:
 - "dispmprt/_DXGKARG_QUERYPROBEDBARS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_QUERYPROBEDBARS, DXGKARG_QUERYPROBEDBARS, *PDXGKARG_QUERYPROBEDBARS, 
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
req.typenames: DXGKARG_QUERYPROBEDBARS, *PDXGKARG_QUERYPROBEDBARS
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGKARG_QUERYPROBEDBARS
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGKARG_QUERYPROBEDBARS structure

## -description

Query probed base address registers (BARS).

## -struct-fields

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field BaseRegisterValues
 
Pointer to an array of ULONGs bounded by the number of Base Address Registers in a PCI device (currently 6). The driver should fully fill in this array, even if the values are 0. These values represent the PCIe BAR sizes in bytes.  The returned value should be the size, minus -1, and then bitwise not.  For example, a 256MB BAR is represented as 0xF000`0000. This is the same way the PCI bus enumerates BAR sizes. For 64 bit bars (or bars larger than 4GB) two sequential bars are used, with the lower bar setting the PCI_TYPE_64BIT (0x4) bit in the lower bar.

## -remarks

## -see-also
