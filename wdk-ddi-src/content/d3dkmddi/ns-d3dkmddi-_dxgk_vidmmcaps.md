---
UID: NS:d3dkmddi._DXGK_VIDMMCAPS
title: _DXGK_VIDMMCAPS (d3dkmddi.h)
description: The DXGK_VIDMMCAPS structure identifies the video memory management capabilities that a display miniport driver can support.
old-location: display\dxgk_vidmmcaps.htm
ms.assetid: c3df50a0-2388-4760-b6e2-ef6af650d0e2
ms.date: 05/10/2018
ms.keywords: DXGK_VIDMMCAPS, DXGK_VIDMMCAPS structure [Display Devices], DmStructs_0ec3e7bb-c14e-41b8-a148-7f77153972e8.xml, _DXGK_VIDMMCAPS, d3dkmddi/DXGK_VIDMMCAPS, display.dxgk_vidmmcaps
ms.topic: struct
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


The <b>DXGK_VIDMMCAPS</b> structure identifies the video memory management capabilities that a display miniport driver can support.


## -struct-fields




### -field OutOfOrderLock

Specifies whether the driver can lock allocation instances other than the latest instance. The driver typically sets this value for DDI threading and load balancing if a DDI thread must lock a vertex buffer that an application thread had previously locked and discarded.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field DedicatedPagingEngine

This member is reserved and should be set to zero.


### -field PagingEngineCanSwizzle

This member is reserved and should be set to zero.


### -field SectionBackedPrimary

Specifies whether the driver supports section-backed primary allocations.

Supported starting with Windows 8.


### -field CrossAdapterResource

Specifies whether the driver supports cross-adapter resources in a <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">hybrid system</a>.

Supported starting with Windows 8.1.

Starting in WDDM 2.4, DXGI will be enabling the current hybrid presentation optimizations for the broader scenario wherever rendering is on one GPU and presenting on another GPU’s monitor. This is only possible if both GPUs support cross adapter resources.

The cross adapter resource properties are listed below.

1. The resource can be paged-in only to the aperture GPU memory segment
2. The resource is allocated as shared.
3. The resource must be marked CPU Visible.
4. The allocation will be created by the OS as write-combined.
5. The resource has only one allocation and has the linear format.
6. The resource has standard pitch alignment (128 bytes). The D3DKMT_CROSS_ADAPTER_RESOURCE_PITCH_ALIGNMENT definition is added for the pitch alignment. The resource must be created at the smallest multiple of this alignment that will contain the resource contents.
7. The resource has a standard height alignment (4 rows). The D3DKMT_CROSS_ADAPTER_RESOURCE_HEIGHT_ALIGNMENT is added. The resource must be created at the smallest multiple of this alignment that will contain the resource contents.

```cpp
#define D3DKMT_CROSS_ADAPTER_RESOURCE_PITCH_ALIGNMENT 128

#define D3DKMT_CROSS_ADAPTER_RESOURCE_HEIGHT_ALIGNMENT 4
```

8. The start address of the resource memory is aligned to one page boundary.
9. The resource might be e created as a standard allocation from kernel mode and later opened by the UMD.
10. The resource might be created by the UMD.

The cross adapter allocation could be used as a primary, but the driver will not get information, that is usually provided when the primary is created

### -field VirtualAddressingSupported

Specifies whether the driver supports virtual memory addressing.

To express support for GPU virtual memory addressing, the driver should set the <b>VirtualAddressingSupported</b> cap and <b>GpuMmuSupported</b> or <b>IoMmuSupported</b> caps.
<b>GpuMmuSupported</b> and <b>IoMmuSupported</b> cannot be set at the same time.


Supported starting with Windows 10.


### -field GpuMmuSupported

Specifies whether the adapter supports the <i>GpuMmu</i> model. An adapter cannot support the <i>GpuMmu</i> and the <i>IoMmu</i> models on different engines at the same time.

Supported starting with Windows 10.


### -field IoMmuSupported

Specifies whether the adapter supports the <i>IoMmu</i> model. An adapter cannot support the <i>GpuMmu</i> and the <i>IoMmu</i> models on different engines at the same time.

Supported starting with Windows 10.


### -field ReplicateGdiContent

Specifies whether the adapter supports the replication of GDI content.

Supported starting with Windows 10.


### -field NonCpuVisiblePrimary




### -field ParavirtualizationSupported

The host KMD needs to set the cap if all DDIs are implemented.


### -field Reserved

This member is reserved and should be set to zero.

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (after setting <b>OutOfOrderLock</b>) of the <b>Value</b> member to zeros.

Note that this version of the <b>Reserved</b> member is available only if DXGKDDI_INTERFACE_VERSION &lt; DXGKDDI_INTERFACE_VERSION_WIN7.

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (after setting <b>OutOfOrderLock</b>) of the <b>Value</b> member to zeros.

Note that this version of the <b>Reserved</b> member is available only if DXGKDDI_INTERFACE_VERSION &lt; DXGKDDI_INTERFACE_VERSION_WIN7.


### -field Value


       A 32-bit value.
      


### -field PagingNode

       A 32-bit value.



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>
 

 

