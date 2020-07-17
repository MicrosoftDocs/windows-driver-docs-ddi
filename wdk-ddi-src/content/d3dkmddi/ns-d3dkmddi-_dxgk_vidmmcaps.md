---
UID: NS:d3dkmddi._DXGK_VIDMMCAPS
title: _DXGK_VIDMMCAPS (d3dkmddi.h)
description: The DXGK_VIDMMCAPS structure identifies the video memory management capabilities that a display miniport driver can support.
old-location: display\dxgk_vidmmcaps.htm
ms.assetid: c3df50a0-2388-4760-b6e2-ef6af650d0e2
ms.date: 03/24/2020
keywords: ["_DXGK_VIDMMCAPS structure"]
ms.keywords: DXGK_VIDMMCAPS, DXGK_VIDMMCAPS structure [Display Devices], DmStructs_0ec3e7bb-c14e-41b8-a148-7f77153972e8.xml, _DXGK_VIDMMCAPS, d3dkmddi/DXGK_VIDMMCAPS, display.dxgk_vidmmcaps
f1_keywords:
 - "d3dkmddi/DXGK_VIDMMCAPS"
 - "DXGK_VIDMMCAPS"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_VIDMMCAPS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_VIDMMCAPS
---

# _DXGK_VIDMMCAPS structure

## -description

The **DXGK_VIDMMCAPS** structure identifies the video memory management capabilities that a display miniport driver can support.

## -syntax

```cpp
typedef struct _DXGK_VIDMMCAPS
{
    union
    {
        struct
        {
            UINT    OutOfOrderLock              : 1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7)
            UINT    DedicatedPagingEngine       : 1; // _ADVSCH_
            UINT    PagingEngineCanSwizzle      : 1; // _ADVSCH_
            UINT    SectionBackedPrimary        : 1; // Create primaries using section without need for IO range
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
            UINT    CrossAdapterResource        : 1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
            UINT    VirtualAddressingSupported  : 1;
            UINT    GpuMmuSupported             : 1;  
            UINT    IoMmuSupported              : 1;  
            UINT    ReplicateGdiContent         : 1;  
            UINT    NonCpuVisiblePrimary        : 1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_2)
            UINT    ParavirtualizationSupported : 1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_4)
            UINT    IoMmuSecureModeSupported    : 1;
            UINT    DisableSelfRefreshVRAMInS3  : 1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_7)
            UINT    IoMmuSecureModeRequired     : 1;
            UINT    Reserved                    : 18;
#else  // ! DXGKDDI_INTERFACE_VERSION_WDDM2_4
            UINT    Reserved                    : 19;
#endif // DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_7
#else  // ! DXGKDDI_INTERFACE_VERSION_WDDM2_4
            UINT    Reserved                    : 21;
#endif // DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_4
#else  // ! DXGKDDI_INTERFACE_VERSION_WDDM2_2
            UINT    Reserved                    : 22;
#endif // DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_2
#else  // ! DXGKDDI_INTERFACE_VERSION_WDDM2_0
            UINT    Reserved                    : 27;
#endif // DXGKDDI_INTERFACE_VERSION_WDDM2_0
#else  // ! DXGKDDI_INTERFACE_VERSION_WDDM1_3
            UINT    Reserved                    : 28;
#endif // DXGKDDI_INTERFACE_VERSION_WDDM1_3
#else  // ! DXGKDDI_INTERFACE_VERSION_WIN7
            UINT    Reserved                    : 31;
#endif // DXGKDDI_INTERFACE_VERSION_WIN7
        };
        UINT        Value;
    };
    UINT            PagingNode;
} DXGK_VIDMMCAPS;
```

## -struct-fields

### -field OutOfOrderLock

Specifies whether the driver can lock allocation instances other than the latest instance. The driver typically sets this value for DDI threading and load balancing if a DDI thread must lock a vertex buffer that an application thread had previously locked and discarded. Setting this member is equivalent to setting the first bit of the 32-bit **Value** member (0x00000001).

### -field DedicatedPagingEngine

This member is reserved and should be set to zero.

### -field PagingEngineCanSwizzle

This member is reserved and should be set to zero.

### -field SectionBackedPrimary

Specifies whether the driver supports section-backed primary allocations. Supported starting with Windows 8.

### -field CrossAdapterResource

Specifies whether the driver supports cross-adapter resources in a [hybrid system<](https://docs.microsoft.com/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system). Supported starting with Windows 8.1.

Starting in WDDM 2.4, DXGI will be enabling the current hybrid presentation optimizations for the broader scenario wherever rendering is on one GPU and presenting on another GPU’s monitor. This is only possible if both GPUs support cross adapter resources.

The cross adapter resource properties are listed below.

* The resource can be paged-in only to the aperture GPU memory segment
* The resource is allocated as shared.
* The resource must be marked CPU Visible.
* The allocation will be created by the OS as write-combined.
* The resource has only one allocation and has the linear format.
* The resource has standard pitch alignment (128 bytes). The D3DKMT_CROSS_ADAPTER_RESOURCE_PITCH_ALIGNMENT definition is added for the pitch alignment. The resource must be created at the smallest multiple of this alignment that will contain the resource contents.
* The resource has a standard height alignment (4 rows). The D3DKMT_CROSS_ADAPTER_RESOURCE_HEIGHT_ALIGNMENT is added. The resource must be created at the smallest multiple of this alignment that will contain the resource contents.

```cpp
#define D3DKMT_CROSS_ADAPTER_RESOURCE_PITCH_ALIGNMENT 128

#define D3DKMT_CROSS_ADAPTER_RESOURCE_HEIGHT_ALIGNMENT 4
```

* The start address of the resource memory is aligned to one page boundary.
* The resource might be e created as a standard allocation from kernel mode and later opened by the UMD.
* The resource might be created by the UMD.

The cross adapter allocation could be used as a primary, but the driver will not get information, that is usually provided when the primary is created

### -field VirtualAddressingSupported

Specifies whether the driver supports virtual memory addressing. To express support for GPU virtual memory addressing, the driver should set the **VirtualAddressingSupported** cap and **GpuMmuSupported** or **IoMmuSupported** caps.
**GpuMmuSupported** and **IoMmuSupported** cannot be set at the same time. Supported starting with Windows 10.

### -field GpuMmuSupported

Specifies whether the adapter supports the *GpuMmu* model. An adapter cannot support the *GpuMmu* and the *IoMmu* models on different engines at the same time. See [GpuMmu model](https://docs.microsoft.com/windows-hardware/drivers/display/gpummu-model) for more information. Supported starting with Windows 10.

### -field IoMmuSupported

Specifies whether the adapter supports the *IoMmu* model. An adapter cannot support the *GpuMmu* and the *IoMmu* models on different engines at the same time. See [IoMmu model](https://docs.microsoft.com/windows-hardware/drivers/display/iommu-model) for more information. Supported starting with Windows 10.

### -field ReplicateGdiContent

Specifies whether the adapter supports the replication of GDI content. Supported starting with Windows 10.

### -field NonCpuVisiblePrimary

Indicates that GDI allocations are not required to be CPU visible. Supported starting with Windows 10.

### -field ParavirtualizationSupported

The host KMD needs to set the cap if all DDIs are implemented. Supported starting with Windows 10 version 1703.

### -field IoMmuSecureModeRequired

Indicates that IOMMU hardware and isolation support (referred to by the **IommuSecureModeSupported** flag) is required or the OS will otherwise not start the adapter. Supported starting with Windows 10 version 2004.

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (after setting **OutOfOrderLock**) of the **Value** member to zeros. Note that **Reserved** is available only if DXGKDDI_INTERFACE_VERSION < DXGKDDI_INTERFACE_VERSION_WIN7.

### -field Value

This value is used to operate over the members collectively.

### -field PagingNode

The zero-based index of the node to use for paging operations. If the driver does not set the **MultiEngineAware** bit-field member of the **SchedulingCaps** member of the [**DXGK_DRIVERCAPS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps) structure, the DirectX graphics kernel subsystem ignores the setting of **PagingNode**. This member applies to WDDM 1.x only. In WDDM 2.x, **PagingNode** was moved to [**DXGK_PHYSICALADAPTERCAPS**](ns-d3dkmddi-_dxgk_physicaladaptercaps.md).

## -see-also

[**DXGK_DRIVERCAPS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps)

[**DXGK_PHYSICALADAPTERCAPS**](ns-d3dkmddi-_dxgk_physicaladaptercaps.md)
