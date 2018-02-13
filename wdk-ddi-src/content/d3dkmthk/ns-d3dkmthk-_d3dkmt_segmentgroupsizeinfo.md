---
UID: NS:d3dkmthk._D3DKMT_SEGMENTGROUPSIZEINFO
title: "_D3DKMT_SEGMENTGROUPSIZEINFO"
author: windows-driver-content
description: A structure that holds information about the segment group size.
old-location: display\d3dkmt_segmentgroupsizeinfo.htm
old-project: display
ms.assetid: 4D9D8179-AA55-409B-A733-7346EC06391B
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DKMT_SEGMENTGROUPSIZEINFO, D3DKMT_SEGMENTGROUPSIZEINFO structure [Display Devices], display.d3dkmt_segmentgroupsizeinfo, d3dkmthk/D3DKMT_SEGMENTGROUPSIZEINFO, D3DKMT_SEGMENTGROUPSIZEINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_SEGMENTGROUPSIZEINFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_SEGMENTGROUPSIZEINFO
---

# _D3DKMT_SEGMENTGROUPSIZEINFO structure


## -description


A structure that holds information about the segment group size.


## -syntax


````
typedef struct _D3DKMT_SEGMENTGROUPSIZEINFO {
  UINT32                 PhysicalAdapterIndex;
  D3DKMT_SEGMENTSIZEINFO LegacyInfo;
  ULONGLONG              LocalMemory;
  ULONGLONG              NonLocalMemory;
  ULONGLONG              NonBudgetMemory;
} D3DKMT_SEGMENTGROUPSIZEINFO;
````


## -struct-fields




### -field PhysicalAdapterIndex

An index to the physical adapter.


### -field LegacyInfo

Legacy segment size info.


### -field LocalMemory

The size of local memory.


### -field NonLocalMemory

The size of non-local memory.


### -field NonBudgetMemory

The size of non-budget memory.

