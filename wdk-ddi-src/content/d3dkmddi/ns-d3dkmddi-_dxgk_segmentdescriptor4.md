---
UID: NS:d3dkmddi._DXGK_SEGMENTDESCRIPTOR4
title: DXGK_SEGMENTDESCRIPTOR4 (d3dkmddi.h)
description: Learn more about the DXGK_SEGMENTDESCRIPTOR4 structure.
ms.date: 02/07/2024
keywords: ["DXGK_SEGMENTDESCRIPTOR4 structure"]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
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
 - _DXGK_SEGMENTDESCRIPTOR4
 - DXGK_SEGMENTDESCRIPTOR4
---

# DXGK_SEGMENTDESCRIPTOR4 structure

## -description

The **DXGK_SEGMENTDESCRIPTOR4** structure describes a programmable CPU host aperture.

## -struct-fields

### -field Flags

Segment bit field flags

### -field BaseAddress

The physical base address for the segment in the GPU.

### -field Size

The size of the segment in bytes.

### -field CommitLimit

The maximum number of bytes that can be committed to this segment. This value applies to the aperture segment only.

### -field SystemMemoryEndAddress

For segments that are partially composed of system memory, all allocations ending after this address are purged during hibernate.

### -field CpuTranslatedAddress

If **Flags.SupportsCpuHostAperture**==**FALSE** and the segment is CPU visible, this will be the CPU physical base address of the segment.

### -field CpuHostAperture

If **Flags.SupportsCpuHostAperture**==**TRUE**, this will have the CPU address and size of the **CPUHostAperture**.

### -field NumInvalidMemoryRanges

The number of invalid memory ranges in the segment. If this value is not zero, the kernel mode driver will be called with DdiQueryAdapterInfo(DXGKQAITYPE_SEGMENTMEMORYSTATE) to get information about invalid memory ranges.

### -field VprRangeStartOffset

Start offset of the video protected region range, in bytes.

### -field VprRangeSize

Size of the video protected region range, in bytes.

### -field VprAlignment

Alignment of the video protected region range, in bytes. This value applies to both the size and start offset of the video protected region range.

### -field NumVprSupported

Number of supported video protected ranges in the VPR range. A value of zero indicates support for an infinite number.

### -field VprReserveSize

Size of the area in the VPR range that is reserved for the driver/hardware to use, in bytes. A value of zero indicates no reserve.

### -field NumUEFIFrameBufferRanges

Number of UEFI frame buffer ranges in the segment. Supported starting in WDDM 2.2.

## -remarks

This structure is used by a WDDM 2.0 or later kernel-mode display miniport drivers to return information about memory segments in response to a [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function call in which the graphics subsystem specifies the **DXGKQAITYPE_QUERYSEGMENT4** value in the **Type** member of the [**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md) structure.

This structure is pointed to by the **pSegmentDescriptor** member of the [**DXGK_QUERYSEGMENTOUT4**](ns-d3dkmddi-_dxgk_querysegmentout4.md) structure.

## -see-also

[**DXGK_QUERYSEGMENTOUT4**](ns-d3dkmddi-_dxgk_querysegmentout4.md)

[**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
