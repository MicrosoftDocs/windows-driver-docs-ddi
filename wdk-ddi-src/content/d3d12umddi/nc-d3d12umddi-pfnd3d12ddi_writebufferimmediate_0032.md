---
UID: NC:d3d12umddi.PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032
title: PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032 (d3d12umddi.h)
description: Used to create a write buffer.
old-location: display\pfnd3d12ddi_writebufferimmediate_0032.htm
ms.assetid: 73486EA4-F1D8-4649-81C8-1698E1854DED
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032 callback function"]
ms.keywords: PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032, PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032 callback, PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032 callback function [Display Devices], d3d12umddi/PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032, display.pfnd3d12ddi_writebufferimmediate_0032
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032
 - d3d12umddi/PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032
product:
 - Windows
---

# PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032 callback function


## -description

Used to create a write buffer.

## -parameters

### -param Arg1

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Count

The count.

### -param pParams

The parameters for the write buffer.

### -param pModes

The modes for the write buffer.

