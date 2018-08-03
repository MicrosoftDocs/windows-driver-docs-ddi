---
UID: NC:d3d12umddi.PFND3D12DDI_FILLDDITTABLE
title: PFND3D12DDI_FILLDDITTABLE
author: windows-driver-content
description:
ms.assetid: af03fe9b-c950-4045-9234-0e8700262854
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
-	PFND3D12DDI_FILLDDITTABLE
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_FILLDDITTABLE callback function

## -description

Implemented by the client driver to retrieve the [D3D12DDI_DEVICE_FUNCS_VIDEO](ns-d3d12umddi-d3d12ddi_device_funcs_video_0033.md) structure.

## -prototype

```
//Declaration

PFND3D12DDI_FILLDDITTABLE Pfnd3d12ddiFillddittable;

// Definition

HRESULT Pfnd3d12ddiFillddittable
(
	 D3D12DDI_HADAPTER
	 D3D12DDI_TABLE_TYPE
	VOID *
	 SIZE_T
	 UINT
	 D3D12DDI_HRTTABLE
)
{...}

PFND3D12DDI_FILLDDITTABLE


```

## -parameters

### -param D3D12DDI_HADAPTER:
### -param D3D12DDI_TABLE_TYPE:
### -param VOID:
### -param SIZE_T:
### -param UINT:
### -param D3D12DDI_HRTTABLE:



## -returns

Returns an HRESULT value.

