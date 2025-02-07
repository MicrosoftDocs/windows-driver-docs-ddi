---
UID: NS:d3dkmddi._DXGK_QUERYADAPTERINFOFLAGS
title: DXGK_QUERYADAPTERINFOFLAGS (d3dkmddi.h)
description: Used to query graphics adapter information.
ms.date: 02/06/2025
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
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
---

# DXGK_QUERYADAPTERINFOFLAGS structure

## -description

The **DXGK_QUERYADAPTERINFOFLAGS** structure specifies flags to use when querying graphics adapter information.

## -struct-fields

### -field VirtualMachineData

Set when the call comes from a virtual machine.

### -field SecureVirtualMachine

Specifies that the virtual machine runs in secure mode.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

A convenient way to access the flags.

## -remarks

## -see-also

[**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
