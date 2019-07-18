---
UID: NS:dispmprt._DXGKARG_READVIRTUALFUNCTIONCONFIG
title: _DXGKARG_READVIRTUALFUNCTIONCONFIG
author: windows-driver-content
description: Arguments used to read virtual function config.
tech.root: display
ms.assetid: 428800d4-49b5-4b33-a6d0-2167ff511fbb
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: struct
f1_keywords:
 - "dispmprt/_DXGKARG_READVIRTUALFUNCTIONCONFIG"
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
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGKARG_READVIRTUALFUNCTIONCONFIG
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
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
