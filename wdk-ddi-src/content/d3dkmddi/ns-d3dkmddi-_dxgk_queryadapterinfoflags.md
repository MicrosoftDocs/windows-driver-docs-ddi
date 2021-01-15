---
UID: NS:d3dkmddi._DXGK_QUERYADAPTERINFOFLAGS
title: _DXGK_QUERYADAPTERINFOFLAGS (d3dkmddi.h)
description: Used to query graphics adapter information.
ms.date: 10/19/2018
keywords: ["DXGK_QUERYADAPTERINFOFLAGS structure"]
ms.keywords: _DXGK_QUERYADAPTERINFOFLAGS, DXGK_QUERYADAPTERINFOFLAGS,
req.header: d3dkmddi.h
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
req.typenames: DXGK_QUERYADAPTERINFOFLAGS
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGK_QUERYADAPTERINFOFLAGS
 - d3dkmddi/_DXGK_QUERYADAPTERINFOFLAGS
 - DXGK_QUERYADAPTERINFOFLAGS
 - d3dkmddi/DXGK_QUERYADAPTERINFOFLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_QUERYADAPTERINFOFLAGS
 - DXGK_QUERYADAPTERINFOFLAGS
product:
 - Windows
---

# _DXGK_QUERYADAPTERINFOFLAGS structure


## -description

Used to query graphics adapter information.

## -struct-fields

### -field VirtualMachineData

Set when the call comes from a virtual machine.

### -field SecureVirtualMachine

Specifies that the virtual machine runs in secure mode.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

A member in the union that _DXGK_QUERYADAPTERINFOFLAGS contains that can hold a 32-bit value that identifies information about the graphics adapter.

## -remarks

## -see-also

