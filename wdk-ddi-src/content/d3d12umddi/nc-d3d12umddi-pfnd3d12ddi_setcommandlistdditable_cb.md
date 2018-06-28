---
UID: NC:d3d12umddi.PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB
title: PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB
author: windows-driver-content
description:
ms.assetid: d1480f13-37d6-465c-b468-bf7a32bf0523
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
topictype:
-	apiref
apitype:
-	UserDefined
apilocation:
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB
product: Windows
targetos: Windows
---

# PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB callback function

## -description

Implemented by the client driver to ...

## -prototype

```
//Declaration

PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB Pfnd3d12ddiSetcommandlistdditableCb;

// Definition

VOID Pfnd3d12ddiSetcommandlistdditableCb
(
	 D3D12DDI_HRTCOMMANDLIST
	 D3D12DDI_HRTTABLE
)
{...}

PFND3D12DDI_SETCOMMANDLISTDDITABLE_CB


```

## -parameters

### -param D3D12DDI_HRTCOMMANDLIST:
### -param D3D12DDI_HRTTABLE:



## -returns

Returns VOID.

