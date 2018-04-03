---
UID: NS:d3dkmddi._DXGK_SCHEDULING_LOG_BUFFER
title: _DXGK_SCHEDULING_LOG_BUFFER
author: windows-driver-content
description:
ms.assetid: a8769b62-4f90-43f8-ab7d-3c0b0fa30f03
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	_DXGK_SCHEDULING_LOG_BUFFER
product: Windows
targetos: Windows
---

# _DXGK_SCHEDULING_LOG_BUFFER structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Information about the passed buffer as a scheduling log for a particular GPU node.

## -struct-fields

### -field Header

Pointer to a DXGK_SCHEDULING_LOG_HEADER structure that contains information about the scheduling log header.

### -field Entries

Pointer to DXGK_SCHEDULING_LOG_ENTRY that contains information about the scheduling log entry.

## -remarks

## -see-also