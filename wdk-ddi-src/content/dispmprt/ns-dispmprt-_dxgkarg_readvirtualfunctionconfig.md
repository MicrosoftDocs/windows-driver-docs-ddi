---
UID: NS:dispmprt._DXGKARG_READVIRTUALFUNCTIONCONFIG
title: _DXGKARG_READVIRTUALFUNCTIONCONFIG
description: Arguments used to read virtual function config.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKARG_READVIRTUALFUNCTIONCONFIG structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_READVIRTUALFUNCTIONCONFIG, DXGKARG_READVIRTUALFUNCTIONCONFIG, *PDXGKARG_READVIRTUALFUNCTIONCONFIG,
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
req.typenames: DXGKARG_READVIRTUALFUNCTIONCONFIG, *PDXGKARG_READVIRTUALFUNCTIONCONFIG
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKARG_READVIRTUALFUNCTIONCONFIG
 - dispmprt/_DXGKARG_READVIRTUALFUNCTIONCONFIG
 - PDXGKARG_READVIRTUALFUNCTIONCONFIG
 - dispmprt/PDXGKARG_READVIRTUALFUNCTIONCONFIG
 - DXGKARG_READVIRTUALFUNCTIONCONFIG
 - dispmprt/DXGKARG_READVIRTUALFUNCTIONCONFIG
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_READVIRTUALFUNCTIONCONFIG
 - PDXGKARG_READVIRTUALFUNCTIONCONFIG
 - DXGKARG_READVIRTUALFUNCTIONCONFIG
product:
 - Windows
dev_langs:
 - c++
---

# _DXGKARG_READVIRTUALFUNCTIONCONFIG structure


## -description

Arguments used to read virtual function config.

## -struct-fields

### -field Data

A buffer which will contain the data read from the Virtual Function’s configuration space.

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field Offset

The offset into the Virtual Function’s configuration space where this read will begin.

### -field Length

 
The length in bytes.

## -remarks

## -see-also

