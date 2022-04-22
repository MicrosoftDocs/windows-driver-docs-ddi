---
UID: NS:d3dkmddi._DXGK_ALLOCATIONLIST
title: DXGK_ALLOCATIONLIST (d3dkmddi.h)
description: The DXGK_ALLOCATIONLIST structure describes an allocation specification that is used in direct memory access (DMA) buffering.
old-location: display\dxgk_allocationlist.htm
ms.date: 04/22/2022
keywords: ["DXGK_ALLOCATIONLIST structure"]
ms.keywords: DXGK_ALLOCATIONLIST, DXGK_ALLOCATIONLIST structure [Display Devices], DmStructs_ed92f9cf-ad3f-4566-89ff-31d6b162f755.xml, _DXGK_ALLOCATIONLIST, d3dkmddi/DXGK_ALLOCATIONLIST, display.dxgk_allocationlist
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
targetos: Windows
tech.root: display
req.typenames: DXGK_ALLOCATIONLIST
f1_keywords:
 - _DXGK_ALLOCATIONLIST
 - d3dkmddi/_DXGK_ALLOCATIONLIST
 - DXGK_ALLOCATIONLIST
 - d3dkmddi/DXGK_ALLOCATIONLIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_ALLOCATIONLIST
 - DXGK_ALLOCATIONLIST
---

# DXGK_ALLOCATIONLIST structure

## -description

The **DXGK_ALLOCATIONLIST** structure describes an allocation specification that is used in direct memory access (DMA) buffering.

## -syntax

``` C
typedef struct _DXGK_ALLOCATIONLIST
{
    HANDLE              hDeviceSpecificAllocation;
    struct
    {
        UINT            WriteOperation  : 1;    // 0x00000001
        UINT            SegmentId       : 5;    // 0x0000002E
        UINT            Reserved        : 26;   // 0xFFFFFFC0
    };
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
    union
    {
        PHYSICAL_ADDRESS        PhysicalAddress;
        D3DGPU_VIRTUAL_ADDRESS  VirtualAddress;
    };
#else // (DXGKDDI_INTERFACE_VERSION < DXGKDDI_INTERFACE_VERSION_WDDM2_0)
    PHYSICAL_ADDRESS    PhysicalAddress;
#endif // (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
} DXGK_ALLOCATIONLIST;
```

## -struct-fields

### -field hDeviceSpecificAllocation [in/out]

An open handle to the allocation that is being referenced (that is, the handle that the driver returned in the **hDeviceSpecificAllocation** member of the [**DXGK_OPENALLOCATIONINFO**](ns-d3dkmddi-_dxgk_openallocationinfo.md) structure for the allocation in a call to the driver's [**DxgkDdiOpenAllocation**](nc-d3dkmddi-dxgkddi_openallocationinfo.md) function).

### -field WriteOperation [in/out]

Identifies whether the allocation can be written to. Setting this member to 1 indicates that the allocation can be written to anywhere in the DMA buffer. Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).

### -field SegmentId [in/out]

Specifies the identifier of a segment that the allocation was last paged in at. Setting this member to 0 indicates that no pre-patching information is available. Setting this member is equivalent to setting the second through sixth bit of a 32-bit value (0x0000002E).

### -field Reserved [in]

Reserved. This member should be set to 0. Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros.

### -field PhysicalAddress [in/out]

A **PHYSICAL_ADDRESS** data type (which is defined as **LARGE_INTEGER**) that indicates the physical address, within the segment that **SegmentId** specifies, where the allocation was last paged-in at. This member is set to zero if no pre-patching information is available.

Supported starting with Windows 10.

### -field  VirtualAddress [in/out]

A **D3DGPU_VIRTUAL_ADDRESS** data type (which is defined as a **ULONGLONG**) that indicates the virtual address.

Supported starting with Windows 10.

## -remarks

In the display miniport driver's [**DxgkDdiRender**](nc-d3dkmddi-dxgkddi_render.md) function, the driver generates a list of **DXGK_ALLOCATIONLIST** structures for allocation specifications that will be used in a direct memory access (DMA) buffer. The video memory manager uses the list to split and patch DMA buffers appropriately.

## -see-also

[**DXGKARG_CREATEALLOCATION**](ns-d3dkmddi-_dxgkarg_createallocation.md)

[**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md)

[**DXGK_OPENALLOCATIONINFO**](ns-d3dkmddi-_dxgk_openallocationinfo.md)

[**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md)

[**DxgkDdiOpenAllocation**](nc-d3dkmddi-dxgkddi_openallocationinfo.md)

[**DxgkDdiRender**](nc-d3dkmddi-dxgkddi_render.md)
