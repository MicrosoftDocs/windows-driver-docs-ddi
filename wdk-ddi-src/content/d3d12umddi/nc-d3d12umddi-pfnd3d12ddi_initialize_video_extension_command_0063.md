---
UID: NC:d3d12umddi.PFND3D12DDI_INITIALIZE_VIDEO_EXTENSION_COMMAND_0063
title: PFND3D12DDI_INITIALIZE_VIDEO_EXTENSION_COMMAND_0063
author: windows-driver-content
description: Records a command to initialize or re-initialize a Video Extension Command into a command list.
tech.root: display
ms.assetid: 31b11f16-b9ae-44d0-a29c-696536cc66cb
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
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
 - PFND3D12DDI_INITIALIZE_VIDEO_EXTENSION_COMMAND_0063
product:
- Windows
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# PFND3D12DDI_INITIALIZE_VIDEO_EXTENSION_COMMAND_0063 callback function

## -description

Records a command to initialize or re-initialize a Video Extension Command into a command list.

## -prototype

```
//Declaration

PFND3D12DDI_INITIALIZE_VIDEO_EXTENSION_COMMAND_0063 Pfnd3d12ddiInitializeVideoExtensionCommand0063; 

// Definition

HRESULT Pfnd3d12ddiInitializeVideoExtensionCommand0063 
(
	D3D12DDI_HCOMMANDLIST hDrvCommandList
	D3D12DDI_HVIDEOEXTENSIONCOMMAND_0063 hDrvVideoExtensionCommand
	 const void *pInitializationParameters
	SIZE_T InitializationParametersSizeInBytes
)
{...}

```

## -parameters

### -param hDrvCommandList

Handle for the command list.

### -param hDrvVideoExtensionCommand

Handle to the video extension command to initialize.

### -param *pInitializationParameters

Pointer to the initialization parameters structure. Parameters for this structure must match the parameter enumeration for [D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063_INITIALIZATION](ne-d3d12umddi-d3d12ddi_video_extension_command_parameter_stage_0063.md).

### -param InitializationParametersSizeInBytes

The size of the initialization parameters structure in bytes.

## -returns

The following error codes are allowed:

|Return value | Description|
|---|---|
|S_OK|Initialization succeeded.|
|D3DDDIERR_APPLICATIONERROR|The caller has attempted to initialize the command incorrectly. For example, provided an invalid argument. This error puts the command list in error and an error code is returned from the Close method on the API command list.|
|D3DDDIERR_DEVICEREMOVED|Cannot initialize the command because the device is in a device removed state. If the runtime has not already realized that the device was removed, this will set the device and command list in error.|


## -remarks


## -see-also
