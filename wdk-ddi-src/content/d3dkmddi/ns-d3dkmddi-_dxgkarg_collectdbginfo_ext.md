---
UID: NS:d3dkmddi._DXGKARG_COLLECTDBGINFO_EXT
title: _DXGKARG_COLLECTDBGINFO_EXT (d3dkmddi.h)
description: The DXGKARG_COLLECTDBGINFO_EXT structure describes extension information for a debug report.
old-location: display\dxgkarg_collectdbginfo_ext.htm
ms.assetid: cbde31fe-06c1-44af-8940-b66e8044a5cd
ms.date: 05/10/2018
ms.keywords: DXGKARG_COLLECTDBGINFO_EXT, DXGKARG_COLLECTDBGINFO_EXT structure [Display Devices], DmStructs_3c280734-d3c8-4970-a6d8-8ad2b3dce913.xml, _DXGKARG_COLLECTDBGINFO_EXT, d3dkmddi/DXGKARG_COLLECTDBGINFO_EXT, display.dxgkarg_collectdbginfo_ext
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGKARG_COLLECTDBGINFO_EXT"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGKARG_COLLECTDBGINFO_EXT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_COLLECTDBGINFO_EXT
---

# _DXGKARG_COLLECTDBGINFO_EXT structure


## -description


The DXGKARG_COLLECTDBGINFO_EXT structure describes extension information for a debug report.


## -struct-fields




### -field BucketingKey

[out] The optional integer key for Microsoft Online Crash Analysis (OCA) bucketing (that is, the categorizing of minidumps). 


### -field CurrentDmaBufferOffset

[out] The optional execution offset into the current DMA buffer. The operating system uses the offset to optimize DMA data collection.


### -field Reserved2

Reserved for future use.


### -field Reserved3

Reserved for future use.


### -field Reserved4

Reserved for future use.


### -field Reserved5

Reserved for future use.


### -field Reserved6

Reserved for future use.


### -field Reserved7

Reserved for future use.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_collectdbginfo">DXGKARG_COLLECTDBGINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_collectdbginfo">DxgkDdiCollectDbgInfo</a>
 

 

