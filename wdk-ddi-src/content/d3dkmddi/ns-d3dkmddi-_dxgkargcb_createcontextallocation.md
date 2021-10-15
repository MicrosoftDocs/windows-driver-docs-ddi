---
UID: NS:d3dkmddi._DXGKARGCB_CREATECONTEXTALLOCATION
title: DXGKARGCB_CREATECONTEXTALLOCATION (d3dkmddi.h)
description: Specifies the allocation attributes of a GPU context or device-specific context.
old-location: display\dxgkargcb_createcontextallocation.htm
ms.date: 10/13/2021
keywords: ["DXGKARGCB_CREATECONTEXTALLOCATION structure"]
ms.keywords: "*INOUT_PDXGKARGCB_CREATECONTEXTALLOCATION, DXGKARGCB_CREATECONTEXTALLOCATION, DXGKARGCB_CREATECONTEXTALLOCATION structure [Display Devices], _DXGKARGCB_CREATECONTEXTALLOCATION, d3dkmddi/DXGKARGCB_CREATECONTEXTALLOCATION, display.dxgkargcb_createcontextallocation"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8 (WDDM 1.2)
req.target-min-winversvr: Windows Server 2012
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
req.typenames: DXGKARGCB_CREATECONTEXTALLOCATION
f1_keywords:
 - _DXGKARGCB_CREATECONTEXTALLOCATION
 - d3dkmddi/_DXGKARGCB_CREATECONTEXTALLOCATION
 - DXGKARGCB_CREATECONTEXTALLOCATION
 - d3dkmddi/DXGKARGCB_CREATECONTEXTALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - _DXGKARGCB_CREATECONTEXTALLOCATION
 - DXGKARGCB_CREATECONTEXTALLOCATION
---

# DXGKARGCB_CREATECONTEXTALLOCATION structure

## -description

The **DXGKARGCB_CREATECONTEXTALLOCATION** structure contains the allocation attributes of a GPU context or device-specific context used in the [**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md) callback function.

## -struct-fields

### -field ContextAllocationFlags

[in] A [**DXGK_CREATECONTEXTALLOCATIONFLAGS**](ns-d3dkmddi-_dxgk_createcontextallocationflags.md) structure that specifies the properties of the allocation.

### -field hAdapter

[in] A handle to the graphics adapter for which the context allocation is created.

### -field hDevice

[in] A handle to the display device that was originally passed by the DirectX graphics subsystem to the display miniport driver's [**DxgkDdiCreateDevice**](nc-d3dkmddi-dxgkddi_createdevice.md) function.

> [!NOTE]
>
> This member is set to NULL for a system device.

### -field hContext

[in] If **ContextAllocationFlags.SharedAcrossContexts** is set to a value of 0, this member contains the value assigned by the DirectX graphics subsystem for the context that was passed to the [**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md) function.

If **ContextAllocationFlags.SharedAcrossContexts** is set to a value of 1, this member should be set to **NULL**.

> [!NOTE]
>
> This member is also set to NULL for a system context.

### -field hDriverAllocation

[in] A handle created by the display miniport driver that identifies the created allocation. The value of this member is subsequently passed as the **Transfer.hAllocation** member of the [**DXGKARG_BUILDPAGINGBUFFER**](ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md) structure that is pointed to by the **pBuildPagingBuffer** parameter of the [**DxgkDdiBuildPagingBuffer**](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) function.

### -field Size

[in] The size, in bytes, that is required for the allocation.

### -field Alignment

[in] The required alignment, in bytes, for the allocation.

### -field SupportedSegmentSet

[in] Segment identifiers that the display miniport driver can set in the **PreferredSegment** member for read or write operations.

### -field EvictionSegmentSet

[in] Identifiers of segments that can be used for eviction.

### -field PreferredSegment

[in] A [**DXGK_SEGMENTPREFERENCE**](/previous-versions/windows/hardware/drivers/ff562047(v=vs.85)) structure that indicates the preferred segment identifiers that the display miniport driver requests that the video memory manager use to page-in the allocation.

### -field HintedBank

[in] A [**DXGK_SEGMENTBANKPREFERENCE**](ns-d3dkmddi-_dxgk_segmentbankpreference.md) structure that indicates the bank ordering preferences that the display miniport driver requests that the video memory manager use to page-in the allocation.

### -field Flags

[in] A [**DXGK_ALLOCATIONINFOFLAGS**](ns-d3dkmddi-_dxgk_allocationinfoflags.md) structure that identifies properties for an allocation in bit-field flags. These properties indicate the type of allocation to create. The display miniport driver specifies these flags for the video memory manager. See Remarks for restrictions on flag values.

### -field hAllocation

[out] A handle that has been assigned by the DirectX graphics subsystem to the allocation. This value is subsequently passed as the **hAllocation** parameter of the  [**DXGKCB_DESTROYCONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_destroycontextallocation.md) function.

### -field PhysicalAdapterIndex

[in] The index of the physical adapter. This field is available starting in WDDM 2.0.

## -remarks

The display miniport driver calls [**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md) to allocate a GPU context or device-specific context. When the driver calls this function, it passes a pointer to a **DXGKARGCB_CREATECONTEXTALLOCATION** structure through the **ContextAllocation** parameter.

## -see-also

[**DXGK_ALLOCATIONINFOFLAGS**](ns-d3dkmddi-_dxgk_allocationinfoflags.md)

[**DXGK_CREATECONTEXTALLOCATIONFLAGS**](ns-d3dkmddi-_dxgk_createcontextallocationflags.md)

[**DXGK_SEGMENTBANKPREFERENCE**](ns-d3dkmddi-_dxgk_segmentbankpreference.md)

[**DXGK_SEGMENTPREFERENCE**](/previous-versions/windows/hardware/drivers/ff562047(v=vs.85))

[**DXGKCB_CREATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_createcontextallocation.md)

[**DXGKCB_DESTROYCONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_destroycontextallocation.md)
