---
UID: NS:d3dkmddi._DXGK_SEGMENTDESCRIPTOR4
title: _DXGK_SEGMENTDESCRIPTOR4 (d3dkmddi.h)
description: The DXGK_SEGMENTDESCRIPTOR4 structure describes a programmable CPU host aperture.
old-location: display\dxgk_segmentdescriptor4.htm
ms.date: 05/10/2018
keywords: ["DXGK_SEGMENTDESCRIPTOR4 structure"]
ms.keywords: DXGK_SEGMENTDESCRIPTOR4, DXGK_SEGMENTDESCRIPTOR4 structure [Display Devices], _DXGK_SEGMENTDESCRIPTOR4, d3dkmddi/DXGK_SEGMENTDESCRIPTOR4, display.dxgk_segmentdescriptor4
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
targetos: Windows
tech.root: display
req.typenames: DXGK_SEGMENTDESCRIPTOR4
f1_keywords:
 - _DXGK_SEGMENTDESCRIPTOR4
 - d3dkmddi/_DXGK_SEGMENTDESCRIPTOR4
 - DXGK_SEGMENTDESCRIPTOR4
 - d3dkmddi/DXGK_SEGMENTDESCRIPTOR4
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_SEGMENTDESCRIPTOR4
---

# _DXGK_SEGMENTDESCRIPTOR4 structure


## -description

The <b>DXGK_SEGMENTDESCRIPTOR4</b> structure describes a programmable CPU host aperture.

## -struct-fields

### -field Flags

Segment bit field flags

### -field BaseAddress

The physical base address for the segment in the GPU.

### -field Size

The size of the segment in bytes.

### -field CommitLimit

The maximum number of bytes that can be committed to this segment. 

<div class="alert"><b>Note</b>  This applies to the aperture segment only.</div>
<div> </div>

### -field SystemMemoryEndAddress

For segments that are partially composed of system memory, all allocations ending after this address are purged during hibernate.

### -field CpuTranslatedAddress

If <b>Flags.SupportsCpuHostAperture</b>==<b>FALSE</b> and the segment is CPU visible, this will be the CPU physical base address of the segment.

### -field CpuHostAperture

If <b>Flags.SupportsCpuHostAperture</b>==<b>TRUE</b>, this will have the CPU address and size of the <b>CPUHostAperture</b>.

### -field NumInvalidMemoryRanges

The number of invalid memory ranges in the segment. If this value is not zero, the kernel mode driver will be called with DdiQueryAdapterInfo(DXGKQAITYPE_SEGMENTMEMORYSTATE) to get information about invalid memory ranges.

### -field VprRangeStartOffset

### -field VprRangeSize

### -field VprAlignment

### -field NumVprSupported

### -field VprReserveSize

### -field NumUEFIFrameBufferRanges

