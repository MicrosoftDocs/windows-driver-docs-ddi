---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOEXTENSIONCOMMAND_0063
title: PFND3D12DDI_CREATEVIDEOEXTENSIONCOMMAND_0063
author: windows-driver-content
description: Creates a video extension command.
tech.root: display
ms.assetid: f7ad7c05-c20c-4211-88bd-e55ae094d3c3
ms.author: windowsdriverdev
ms.date: 04/04/2019
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CREATEVIDEOEXTENSIONCOMMAND_0063"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEVIDEOEXTENSIONCOMMAND_0063
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATEVIDEOEXTENSIONCOMMAND_0063 callback function

## -description

Creates a video extension command. All significant internal resource allocations used by the extension command should be created during video extension creation.

## -parameters

### -param hDrvDevice

Handle for the Direct3D 12 device.

### -param pArgs

Pointer to a [D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063](ns-d3d12umddi-d3d12ddiarg_create_video_extension_command_0063.md) structure that contains arguments.

### -param hDrvVideoExtensionCommand

A handle to a video extension command D3D12DDI_HVIDEOEXTENSIONCOMMAND_0063.

## -returns

Returns HRESULT.

## -prototype

```
//Declaration

PFND3D12DDI_CREATEVIDEOEXTENSIONCOMMAND_0063 Pfnd3d12ddiCreatevideoextensioncommand0063; 

// Definition

HRESULT Pfnd3d12ddiCreatevideoextensioncommand0063 
(
	D3D12DDI_HDEVICE hDrvDevice
	 const D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063 *pArgs
	D3D12DDI_HVIDEOEXTENSIONCOMMAND_0063 hDrvVideoExtensionCommand
)
{...}

```

## -remarks

## -see-also

