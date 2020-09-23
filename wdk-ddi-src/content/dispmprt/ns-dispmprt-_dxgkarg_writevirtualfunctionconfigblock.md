---
UID: NS:dispmprt._DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK
title: _DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK
description: Used to write a virtual function configuration block.
tech.root: display
ms.assetid: 6705ef8c-c3f0-4b8a-8230-0e5952ba30d5
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK, DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK, *PDXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK,
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
req.typenames: DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK, *PDXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK
 - dispmprt/_DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK
 - PDXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK
 - dispmprt/PDXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK
 - DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK
 - dispmprt/DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK
product:
 - Windows
dev_langs:
 - c++
---

# _DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK structure


## -description

Used to write a virtual function configuration block.

## -struct-fields

### -field Data

A buffer which will contain the data read from the Virtual Function’s configuration space.

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field BlockId

Number identifying the block to be written. This is defined by the provider of the Physical Function driver.

### -field Length

The length in bytes.

## -remarks

## -see-also

