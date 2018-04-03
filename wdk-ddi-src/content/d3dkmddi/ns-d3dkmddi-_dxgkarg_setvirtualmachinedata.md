---
UID: NS:d3dkmddi._DXGKARG_SETVIRTUALMACHINEDATA
title: _DXGKARG_SETVIRTUALMACHINEDATA
author: windows-driver-content
description:
ms.assetid: abccb1a3-74bd-4831-9b69-50974ba2b997
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	_DXGKARG_SETVIRTUALMACHINEDATA
product: Windows
targetos: Windows
---

# _DXGKARG_SETVIRTUALMACHINEDATA structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

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