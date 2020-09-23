---
UID: NS:dispmprt._DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK
title: _DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK
description: Arguments used to read virtual function config block.
tech.root: display
ms.assetid: 0b5a0ae9-7b8d-436d-a5b2-17a3daea4bec
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK, DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK, *PDXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK,
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
req.typenames: DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK, *PDXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK
 - dispmprt/_DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK
 - PDXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK
 - dispmprt/PDXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK
 - DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK
 - dispmprt/DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK
product:
 - Windows
dev_langs:
 - c++
---

# _DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK structure


## -description

Arguments used to read virtual function config block.

## -struct-fields

### -field Data

A buffer which will contain the data read from the Virtual Function’s configuration space.

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field BlockId

Number identifying the block to be read. This is defined by the provider of the Physical Function driver.

### -field Length

 
The length in bytes.

## -remarks

## -see-also

