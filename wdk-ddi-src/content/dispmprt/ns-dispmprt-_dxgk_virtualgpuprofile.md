---
UID: NS:dispmprt._DXGK_VIRTUALGPUPROFILE
title: _DXGK_VIRTUALGPUPROFILE
author: windows-driver-content
description: Information about a virtual GPU profile.
tech.root: display
ms.assetid: be1bbb29-bb8c-4948-bebd-7c9dabb2dfd6
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_VIRTUALGPUPROFILE, DXGK_VIRTUALGPUPROFILE, *PDXGK_VIRTUALGPUPROFILE, 
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: 
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_VIRTUALGPUPROFILE, *PDXGK_VIRTUALGPUPROFILE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGK_VIRTUALGPUPROFILE
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# _DXGK_VIRTUALGPUPROFILE structure

## -description

Information about a virtual GPU profile.

## -struct-fields

### -field Capability

The array of capability values, which include Memory, Encode, Decode and Compute. A minimum, maximum and optimal values are specified for each capability. When the vGPU is running, each capability cannot be lower than MinValue and more than MaxValue. The driver could assign the current capability value based in the physical GPU load.

## -remarks



## -see-also
