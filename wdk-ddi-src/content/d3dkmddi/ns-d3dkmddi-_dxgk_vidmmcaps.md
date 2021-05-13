---
UID: NS:d3dkmddi._DXGK_VIDMMCAPS
title: DXGK_VIDMMCAPS (d3dkmddi.h)
description: The DXGK_VIDMMCAPS structure identifies the video memory management capabilities that a display miniport driver can support.
old-location: display\dxgk_vidmmcaps.htm
ms.date: 05/13/2021
keywords: ["DXGK_VIDMMCAPS structure"]
ms.keywords: DXGK_VIDMMCAPS, DXGK_VIDMMCAPS structure [Display Devices], DmStructs_0ec3e7bb-c14e-41b8-a148-7f77153972e8.xml, _DXGK_VIDMMCAPS, d3dkmddi/DXGK_VIDMMCAPS, display.dxgk_vidmmcaps
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: DXGK_VIDMMCAPS
f1_keywords:
 - _DXGK_VIDMMCAPS
 - d3dkmddi/_DXGK_VIDMMCAPS
 - DXGK_VIDMMCAPS
 - d3dkmddi/DXGK_VIDMMCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_VIDMMCAPS
 - DXGK_VIDMMCAPS
---

# DXGK_VIDMMCAPS structure

## -description

The **DXGK_VIDMMCAPS** structure identifies the video memory management capabilities that a display miniport driver supports.

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

Specifies whether the driver provides tier 1 support of copying to and from cross-adapter resources in a [hybrid system<](/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system). Supported starting with Windows 8.1.

Starting in WDDM 2.4, DXGI enables the current hybrid presentation optimizations for the broader scenario wherever rendering is on one GPU and presenting on another GPU’s monitor. This is only possible if both GPUs support cross-adapter resources.

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

Specifies whether the adapter supports the *GpuMmu* model. An adapter cannot support the *GpuMmu* and the *IoMmu* models on different engines at the same time. See [GpuMmu model](/windows-hardware/drivers/display/gpummu-model) for more information. Supported starting with Windows 10.

### -field IoMmuSupported

Specifies whether the adapter supports the *IoMmu* model. An adapter cannot support the *GpuMmu* and the *IoMmu* models on different engines at the same time. See [IoMmu model](/windows-hardware/drivers/display/iommu-model) for more information. Supported starting with Windows 10.

### -field ReplicateGdiContent

Specifies whether the adapter supports the replication of GDI content. Supported starting with Windows 10.

### -field NonCpuVisiblePrimary

Indicates that GDI allocations are not required to be CPU visible. Supported starting with Windows 10.

### -field ParavirtualizationSupported

The host KMD needs to set the cap if all DDIs are implemented. Supported starting with Windows 10 version 1703.

### -field IoMmuSecureModeSupported

Indicates that the driver supports IOMMU hardware and isolation. Supported starting with Windows 10 version 1803.

### -field DisableSelfRefreshVRAMInS3

Disable support for VRAM self-refresh in S3. Supported starting with Windows 10 version 1803.

### -field IoMmuSecureModeRequired

Indicates that IOMMU hardware and isolation support (referred to by the **IommuSecureModeSupported** flag) is required or the OS will otherwise not start the adapter. Supported starting with Windows 10 version 2004.

### -field MapAperture2Supported

Supported starting with Windows Server 2022.

### -field CrossAdapterResourceTexture

Specifies whether the driver provides tier 2 support of texturing from cross-adapter resources. A driver that indicates support for **CrossAdapterResourceTexture** must also indicate support for **CrossAdapterResource**. Supported starting with WDDM version 2.9.

### -field CrossAdapterResourceScanout

Specifies whether the driver provides tier 3 support of scanning out cross-adapter resources. A driver that indicates support for **CrossAdapterResourceScanout** must also indicate support for **CrossAdapterResource** and **CrossAdapterResourceTexture**. Supported starting with WDDM version 2.9.

Tier 3 support requires that the driver be able to perform the supported flipping capabilities, declared by driver in [**DXGK_FLIPCAPS**](ns-d3dkmddi-_dxgk_flipcaps.md), for cross-adapter resources of the following minimum specifications:

* Cross-adapter primary buffer size of 1920 x 1080 or smaller
* Buffer pixel format of any of the following supported DisplayScanOut formats:
  * DXGI_FORMAT_R16G16B16A16_FLOAT
  * DXGI_FORMAT_R10G10B10A2_UNORM
  * DXGI_FORMAT_R8G8B8A8_UNORM
  * DXGI_FORMAT_R8G8B8A8_UNORM_SRGB
  * DXGI_FORMAT_B8G8R8A8_UNORM
  * DXGI_FORMAT_R10G10B10_XR_BIAS_A2_UNORM
  * DXGI_FORMAT_B8G8R8A8_UNORM_SRGB

The DXGI runtime will query for driver's **CrossAdapterResourceScanout** support and if supported, the presentation stack shall go down the 1 copy path. Therefore, drivers that declare support for **CrossAdapterResourceScanout** are also required to:

* Support [**DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3**](nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport3.md).
* Support all the relevant presentation-related DDIs for cross-adapter primaries of the above minimum specifications. A few examples are pfnCreateResource, pfnCheckMultiplaneOverlaySupport and pfnPresentMultiplaneOverlay/pfnPresent1. Please refer to existing specs for the necessary detail, such as MPO spec  and Hybrid spec. Please refer to the section below for more details about falling out of CASO.

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (after setting **OutOfOrderLock**) of the **Value** member to zeros. Note that **Reserved** is available only if DXGKDDI_INTERFACE_VERSION < DXGKDDI_INTERFACE_VERSION_WIN7.

### -field Value

This value is used to operate over the members collectively.

### -field PagingNode

The zero-based index of the node to use for paging operations. If the driver does not set the **MultiEngineAware** bit-field member of the **SchedulingCaps** member of the [**DXGK_DRIVERCAPS**](./ns-d3dkmddi-_dxgk_drivercaps.md) structure, the DirectX graphics kernel subsystem ignores the setting of **PagingNode**. This member applies to WDDM 1.x only. In WDDM 2.x, **PagingNode** was moved to [**DXGK_PHYSICALADAPTERCAPS**](ns-d3dkmddi-_dxgk_physicaladaptercaps.md).

## -see-also

[**DXGK_DRIVERCAPS**](./ns-d3dkmddi-_dxgk_drivercaps.md)

[**DXGK_PHYSICALADAPTERCAPS**](ns-d3dkmddi-_dxgk_physicaladaptercaps.md)
