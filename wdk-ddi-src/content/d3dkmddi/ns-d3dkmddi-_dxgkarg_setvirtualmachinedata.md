---
UID: NS:d3dkmddi._DXGKARG_SETVIRTUALMACHINEDATA
title: _DXGKARG_SETVIRTUALMACHINEDATA (d3dkmddi.h)
description: Arguments used to set virtual machine data.
ms.assetid: abccb1a3-74bd-4831-9b69-50974ba2b997
ms.date: 10/19/2018
keywords: ["_DXGKARG_SETVIRTUALMACHINEDATA structure"]
f1_keywords:
 - "d3dkmddi/_DXGKARG_SETVIRTUALMACHINEDATA"
 - "_DXGKARG_SETVIRTUALMACHINEDATA"
ms.keywords: _DXGKARG_SETVIRTUALMACHINEDATA, DXGKARG_SETVIRTUALMACHINEDATA,
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
req.typenames: DXGKARG_SETVIRTUALMACHINEDATA
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGKARG_SETVIRTUALMACHINEDATA
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# _DXGKARG_SETVIRTUALMACHINEDATA structure

## -description

Arguments used to set virtual machine data.

## -struct-fields

### -field hKmdVmWorkerProcess

A handle to the kernel mode virtual machine worker process.

### -field pVmGuid

The virtual machine guid.

### -field Flags

Specifies the virtual machine flags.

## -remarks

## -see-also

[DXGKDDI_SETVIRTUALMACHINEDATA](nc-d3dkmddi-dxgkddi_setvirtualmachinedata.md)
