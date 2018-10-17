---
UID: NC:d3dkmthk.PFND3DKMT_UNREGISTERTRIMNOTIFICATION
title: PFND3DKMT_UNREGISTERTRIMNOTIFICATION
author: windows-driver-content
description: PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function removes a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).
ms.assetid: 3e329473-b630-4e29-ace3-7ae0c2606198
ms.date: 
ms.topic: callback
req.header: d3dkmthk.h
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_UNREGISTERTRIMNOTIFICATION
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function

## -description

PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function removes a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).

## -prototype

```
//Declaration

PFND3DKMT_UNREGISTERTRIMNOTIFICATION Pfnd3dkmtUnregistertrimnotification; 

// Definition

NTSTATUS Pfnd3dkmtUnregistertrimnotification 
(
	D3DKMT_UNREGISTERTRIMNOTIFICATION *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_UNREGISTERTRIMNOTIFICATION](ns-d3dkmthk-_d3dkmt_unregistertrimnotification.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
