---
UID: NC:d3dkmddi.DXGKDDI_NOTIFYFOCUSPRESENT
title: DXGKDDI_NOTIFYFOCUSPRESENT
author: windows-driver-content
description: Notifies the GPU scheduler of a particular Present N, and the GPU scheduler will in turn perform the yield check on all GPU nodes and run a yield algorithm if necessary.
ms.assetid: a2d25102-5181-4fb7-abcc-fb0669d9d95c
ms.date:
ms.topic: callback
req.header: d3dkmddi.h
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
-	d3dkmddi.h
api_name:
-	DXGKDDI_NOTIFYFOCUSPRESENT
product:
-	Windows
targetos: Windows
tech.root: display
---

# DXGKDDI_NOTIFYFOCUSPRESENT callback function

## -description

Notifies the GPU scheduler of a particular Present N, and the GPU scheduler will in turn perform the yield check on all GPU nodes and run a yield algorithm if necessary.

## -prototype

```
//Declaration

DXGKDDI_NOTIFYFOCUSPRESENT DxgkddiNotifyfocuspresent;

// Definition

NTSTATUS DxgkddiNotifyfocuspresent
(
	IN_CONST_HANDLE hAdapter
)
{...}

DXGKDDI_NOTIFYFOCUSPRESENT *PDXGKDDI_NOTIFYFOCUSPRESENT


```

## -parameters

### -param hAdapter:

The logical adapter for which a new focus Present has completed. The GPU scheduler will in turn notify all individual GPU engine schedulers of the new present.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

