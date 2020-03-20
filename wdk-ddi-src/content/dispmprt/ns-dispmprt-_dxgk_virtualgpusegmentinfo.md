---
UID: NS:dispmprt._DXGK_VIRTUALGPUSEGMENTINFO
title: _DXGK_VIRTUALGPUSEGMENTINFO
author: windows-driver-content
description: Information about the virtual GPU segment info.
tech.root: display
ms.assetid: 25475970-446a-4dbf-b916-222bc6eb6ba3
ms.author: windowsdriverdev
ms.date: 04/04/2019 
keywords: ["_DXGK_VIRTUALGPUSEGMENTINFO structure"]
f1_keywords:
 - "dispmprt/_DXGK_VIRTUALGPUSEGMENTINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_VIRTUALGPUSEGMENTINFO, DXGK_VIRTUALGPUSEGMENTINFO, *PDXGK_VIRTUALGPUSEGMENTINFO, 
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
req.typenames: DXGK_VIRTUALGPUSEGMENTINFO, *PDXGK_VIRTUALGPUSEGMENTINFO
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGK_VIRTUALGPUSEGMENTINFO
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGK_VIRTUALGPUSEGMENTINFO structure

## -description

Information about the virtual GPU segment info.

## -struct-fields

### -field DriverSegmentId

The driver Id of the physical memory segment, which was enumerated by Dxgkrnl. The value starts from 1.

### -field Size

Size in this memory segment, which is needed in the vGPU.

### -field Alignment

Allocation alignment in the memory segment in bytes. This value must be a multiple of 4096 bytes or zero.

### -field MinSegmentOffset

Optionally, the driver can specify a range in the segment where this allocation must be located. If there is no range restriction, set these values to zero. This could be used, for example, when a portion of the VPR range needs to be assigned to a vGPU. 

> [!NOTE]
> This functionality is deprecated.

### -field MaxSegmentOffset

Optionally, the driver can specify a range in the segment where this allocation must be located. If there is no range restriction, set these values to zero. This could be used, for example, when a portion of the VPR range needs to be assigned to a vGPU. 

> [!NOTE]
> This functionality is deprecated.

### -field PrivateDriverData

Allocation driver private data.

## -remarks

## -see-also
