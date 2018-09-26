---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYPAGINGQUEUE
title: PFND3DKMT_DESTROYPAGINGQUEUE
author: windows-driver-content
description: The PFND3DKMT_DESTROYPAGINGQUEUE callback function destroys paging queue.
ms.assetid: 7d6d38df-9ec0-4d6e-92f3-aecb8f330161
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3DKMT_DESTROYPAGINGQUEUE
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_DESTROYPAGINGQUEUE callback function

## -description

The PFND3DKMT_DESTROYPAGINGQUEUE callback function destroys paging queue.

## -prototype

```
//Declaration

PFND3DKMT_DESTROYPAGINGQUEUE Pfnd3dkmtDestroypagingqueue; 

// Definition

NTSTATUS Pfnd3dkmtDestroypagingqueue 
(
	D3DDDI_DESTROYPAGINGQUEUE *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DDDI_DESTROYPAGINGQUEUE](../d3dukmdt/ns-d3dukmdt-d3dddi_destroypagingqueue.md) structure.

## -returns

Returns NTSTATUS.