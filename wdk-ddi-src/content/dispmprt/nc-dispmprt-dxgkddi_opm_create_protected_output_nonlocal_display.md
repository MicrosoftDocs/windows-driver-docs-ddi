---
UID: NC:dispmprt.DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT_NONLOCAL_DISPLAY
title: DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT_NONLOCAL_DISPLAY
author: windows-driver-content
description: 
tech.root: display
ms.assetid: 8f6c8f1a-ad7f-4de8-a62c-a970df20eabd
ms.author: windowsdriverdev
ms.date: 04/04/2019 
keywords: ["DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT_NONLOCAL_DISPLAY callback function"]
f1_keywords:
 - "dispmprt/DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT_NONLOCAL_DISPLAY"
 - "DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT_NONLOCAL_DISPLAY"
req.header: dispmprt.h
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
 - apiref
api_type: 
 - UserDefined
api_location: 
 - dispmprt.h
api_name: 
 - DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT_NONLOCAL_DISPLAY
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT_NONLOCAL_DISPLAY callback function

## -description



## -prototype

```
//Declaration

DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT_NONLOCAL_DISPLAY DxgkddiOpmCreateProtectedOutputNonlocalDisplay; 

// Definition

NTSTATUS DxgkddiOpmCreateProtectedOutputNonlocalDisplay 
(
	PVOID MiniportDeviceContext
	DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS NewVideoOutputSemantics
	UINT64 OPMEncoderContext
	DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT *pActualOutputFormat
	UINT64 NonLocalOutputId
	DXGKMDT_OPM_CONNECTOR_TYPE NonLocalConnectorType
	PHANDLE NewProtectedOutputHandle
)
{...}

```

## -parameters

### -param MiniportDeviceContext 
### -param NewVideoOutputSemantics: 
### -param OPMEncoderContext 
### -param pActualOutputFormat: 
### -param NonLocalOutputId: 
### -param NonLocalConnectorType: 
### -param NewProtectedOutputHandle: 



## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks




## -see-also
