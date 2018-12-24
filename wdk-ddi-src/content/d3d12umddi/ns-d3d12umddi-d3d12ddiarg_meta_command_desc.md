---
UID: NS:d3d12umddi.D3D12DDIARG_META_COMMAND_DESC
title: D3D12DDIARG_META_COMMAND_DESC
description: The description of a meta-command.
ms.assetid: adcfacdf-0bdc-43c1-9bf6-98853f6073f2
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDIARG_META_COMMAND_DESC, D3D12DDIARG_META_COMMAND_DESC, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDIARG_META_COMMAND_DESC
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_META_COMMAND_DESC
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDIARG_META_COMMAND_DESC structure

## -description

The description of a meta-command. A meta-command is a Direct3D object intended to represent an IHV-accelerated algorithm. It’s an opaque reference to a command generator implemented by the driver.

## -struct-fields

### -field Id

The id of a meta-command.

### -field Name

Pointer to a wide string, the driver allocates and keeps for the lifetime of the device.

### -field InitializationDirtyState

Specifies the command list states that are modified by the initialization call.

### -field ExecutionDirtyState

Specifies the command list states that are modified by the execute call.

## -remarks

## -see-also
