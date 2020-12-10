---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063
title: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063
description: Parameter types are used to enumerate the members of each parameter stage parameter structure.
tech.root: display
ms.date: 04/04/2019
keywords: ["D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063 enumeration"]
ms.keywords: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063, D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063
 - d3d12umddi/D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063 enumeration


## -description

Parameter types are used to enumerate the members of each parameter stage parameter structure. The types supported are fixed, and additional parameter types require changes in order to be supported.

## -enum-fields

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_UINT8

Unsigned 8-bit integer.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_UINT16

Unsigned 16-bit integer.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_UINT32

Unsigned 32-bit integer.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_UINT64

Unsigned 64-bit integer.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_SINT8

Signed 8-bit integer.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_SINT16

Signed 16-bit integer.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_SINT32

Signed 32-bit integer.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_SINT64

Signed 64-bit integer.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_FLOAT

IEEE 32-bit floating point number.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_DOUBLE

IEEE 32-bit double point number.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_RESOURCE

A D3D12DDI_HRESOURCE handle. The caller must use resource barriers to transition to the state appropriate for the parameter:

|D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAG|Read|Write|
|---|---|---|
|D3D12DDI_COMMAND_QUEUE_FLAGS_VIDEO_DECODE|D3D12DDI_RESOURCE_STATE_VIDEO_DECODE_READ|D3D12DDI_RESOURCE_STATE_VIDEO_DECODE_WRITE|
|D3D12DDI_COMMAND_QUEUE_FLAGS_VIDEO_PROCESS|D3D12DDI_RESOURCE_STATE_VIDEO_PROCESS_READ|D3D12DDI_RESOURCE_STATE_VIDEO_PROCESS_WRITE|
|D3D12DDI_COMMAND_QUEUE_FLAGS_VIDEO_ENCODE|D3D12DDI_RESOURCE_STATE_VIDEO_ENCODE_READ|D3D12DDI_RESOURCE_STATE_VIDEO_ENCODE_WRITE|

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_MAX_VALID

The maximum valid number supported.

## -remarks

## -see-also

