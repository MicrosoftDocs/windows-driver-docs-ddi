---
UID: NS:d3dkmddi._DXGK_SCHEDULING_LOG_BUFFER
title: _DXGK_SCHEDULING_LOG_BUFFER (d3dkmddi.h)
description: Information about the passed buffer as a scheduling log for a particular GPU node.
ms.assetid: a8769b62-4f90-43f8-ab7d-3c0b0fa30f03
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dkmddi/_DXGK_SCHEDULING_LOG_BUFFER"
ms.keywords: _DXGK_SCHEDULING_LOG_BUFFER, DXGK_SCHEDULING_LOG_BUFFER,
req.header: d3dkmddi.h
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
req.typenames: DXGK_SCHEDULING_LOG_BUFFER
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGK_SCHEDULING_LOG_BUFFER
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# _DXGK_SCHEDULING_LOG_BUFFER structure

## -description

Information about the passed buffer as a scheduling log for a particular GPU node.

## -struct-fields

### -field Header

Pointer to a [DXGK_SCHEDULING_LOG_HEADER](ns-d3dkmddi-_dxgk_scheduling_log_header.md) structure that contains information about the scheduling log header.

### -field Entries

Pointer to [DXGK_SCHEDULING_LOG_ENTRY](ns-d3dkmddi-_dxgk_scheduling_log_entry.md) that contains information about the scheduling log entry.

## -remarks

## -see-also
