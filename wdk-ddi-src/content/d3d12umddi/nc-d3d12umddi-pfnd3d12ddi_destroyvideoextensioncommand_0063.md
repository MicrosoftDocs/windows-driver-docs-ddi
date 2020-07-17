---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYVIDEOEXTENSIONCOMMAND_0063
title: PFND3D12DDI_DESTROYVIDEOEXTENSIONCOMMAND_0063
author: windows-driver-content
description: Destroys the video extension command.
tech.root: display
ms.assetid: 4312e775-cc75-477b-979b-09fd0604b55c
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["PFND3D12DDI_DESTROYVIDEOEXTENSIONCOMMAND_0063 callback function"]
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_DESTROYVIDEOEXTENSIONCOMMAND_0063"
 - "PFND3D12DDI_DESTROYVIDEOEXTENSIONCOMMAND_0063"
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
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - d3d12umddi.h
api_name: 
 - PFND3D12DDI_DESTROYVIDEOEXTENSIONCOMMAND_0063
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# PFND3D12DDI_DESTROYVIDEOEXTENSIONCOMMAND_0063 callback function

## -description

Destroys the video extension command.

## -prototype

```
//Declaration

PFND3D12DDI_DESTROYVIDEOEXTENSIONCOMMAND_0063 Pfnd3d12ddiDestroyvideoextensioncommand0063; 

// Definition

VOID Pfnd3d12ddiDestroyvideoextensioncommand0063 
(
	D3D12DDI_HDEVICE hDrvDevice
	D3D12DDI_HVIDEOEXTENSIONCOMMAND_0063 hDrvVideoExtensionCommand
)
{...}

```

## -parameters

### -param hDrvDevice

Handle for the Direct3D 12 device.

### -param hDrvVideoExtensionCommand

Handle to the D3D12DDI_HVIDEOEXTENSIONCOMMAND_0063 to be destroyed.

## -remarks


## -see-also
