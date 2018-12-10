---
UID: NS:dxgiddi.DXGIDDICB_SUBMITPRESENTBLTTOHWQUEUE
title: DXGIDDICB_SUBMITPRESENTBLTTOHWQUEUE
author: windows-driver-content
description:
ms.assetid: 23ad4e9d-d5eb-4cd9-80bd-194a6a276e63
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: DXGIDDICB_SUBMITPRESENTBLTTOHWQUEUE, DXGIDDICB_SUBMITPRESENTBLTTOHWQUEUE,
req.header: dxgiddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver: D3D_UMD_INTERFACE_VERSION_WDDM2_4_2
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGIDDICB_SUBMITPRESENTBLTTOHWQUEUE
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	dxgiddi.h
api_name:
-	DXGIDDICB_SUBMITPRESENTBLTTOHWQUEUE
product: 
- Windows
targetos: Windows
tech.root: display
---

# DXGIDDICB_SUBMITPRESENTBLTTOHWQUEUE structure

## -description

Contains arguments needed for the [PfnddxgiddiSubmitPresentBltToHwQueuecb](nc-dxgiddi-pfnddxgiddi_submitpresentblttohwqueuecb.md) function.

## -struct-fields

### -field hSrcAllocation

[in] The allocation of which content will be presented.

### -field hDstAllocation

[in] The destination allocation of the present.

### -field pDXGIContext

Fill this with the value in [DXGI_DDI_ARG_PRESENT.pDXGIContext](ns-dxgiddi-dxgi_ddi_arg_present.md).

### -field hHwQueue

Hardware queue being submitted to.

### -field HwQueueProgressFenceId

Hardware queue progress fence ID that will be signaled when the Present Blt is done on the GPU.

### -field PrivateDriverDataSize

The size of pPrivateDriverData.

### -field pPrivateDriverData

[in] Private driver data to pass to DdiPresent.

