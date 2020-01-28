---
UID: NS:dispmprt._DXGKARG_WRITEVIRTUALFUNCTIONCONFIG
title: _DXGKARG_WRITEVIRTUALFUNCTIONCONFIG
author: windows-driver-content
description: Used to write a virtual function configuration.
tech.root: display
ms.assetid: bd1a1779-458c-4b44-9608-d700a5389bac
ms.author: windowsdriverdev
ms.date: 04/04/2019 
f1_keywords:
 - "dispmprt/_DXGKARG_WRITEVIRTUALFUNCTIONCONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_WRITEVIRTUALFUNCTIONCONFIG, DXGKARG_WRITEVIRTUALFUNCTIONCONFIG, *PDXGKARG_WRITEVIRTUALFUNCTIONCONFIG, 
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
req.typenames: DXGKARG_WRITEVIRTUALFUNCTIONCONFIG, *PDXGKARG_WRITEVIRTUALFUNCTIONCONFIG
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGKARG_WRITEVIRTUALFUNCTIONCONFIG
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGKARG_WRITEVIRTUALFUNCTIONCONFIG structure

## -description

Used to write a virtual function configuration.

## -struct-fields

### -field Data

A buffer which will contain the data read from the Virtual Function’s configuration space.

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field Offset

The offset into the Virtual Function’s configuration space where this write will begin.

### -field Length
 
The length of *Data*.

## -remarks

## -see-also
