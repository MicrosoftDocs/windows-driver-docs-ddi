---
UID: NC:videoagp.PAGP_RESERVE_PHYSICAL
title: PAGP_RESERVE_PHYSICAL (videoagp.h)
description: Learn more about the PAGP_RESERVE_PHYSICAL callback function.
tech.root: display
ms.date: 11/01/2024
keywords: ["PAGP_RESERVE_PHYSICAL callback function"]
req.header: videoagp.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 2000
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
req.typenames: 
f1_keywords:
 - PAGP_RESERVE_PHYSICAL
 - videoagp/PAGP_RESERVE_PHYSICAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - videoagp.h
api_name:
 - PAGP_RESERVE_PHYSICAL
---

## -description

The **AgpReservePhysical** function reserves a range of physical addresses on the system bus to which the AGP controller can respond.

## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.

### -param Pages [in]

Specifies the number of pages that the video port driver should reserve.

### -param Caching [in]

A [**VIDEO_PORT_CACHE_TYPE**](ne-videoagp-video_port_cache_type.md) enumeration that specifies the type of caching that the system should use.

### -param PhysicalReserveContext [out]

Specifies the location in which the video port driver writes a context handle that identifies the reserved physical address space.

## -returns

**AgpReservePhysical** returns the base address of the reserved physical address range if successful; otherwise, it returns NULL.

## -remarks

Video miniport drivers that run on Windows 2000 should always reserve a range whose size is a multiple of 64 kilobytes. Reserving a range that is not a multiple of 64 kilobytes can result in [**AgpReserveVirtual**](nc-videoagp-pagp_reserve_virtual.md) or [**AgpCommitVirtual**](nc-videoagp-pagp_commit_virtual.md) returning an invalid virtual address.

On Windows XP and later, **AgpReservePhysical** automatically expands the requested range to a multiple of 64 kilobytes.

Upon successful return, the AGP controller can respond to the reserved physical address range on the bus. However, the video miniport driver must first call [**AgpCommitPhysical**](nc-videoagp-pagp_commit_physical.md) to cause this memory to be committed before accessing it in order for the accessed results to be defined.

The miniport driver can call **AgpReservePhysical** several times to reserve many smaller address ranges rather than one big range.

The miniport driver should call [**AgpReleasePhysical**](nc-videoagp-pagp_release_physical.md) to release the physical address range when it is no longer needed.

## -see-also

[**AgpCommitPhysical**](nc-videoagp-pagp_commit_physical.md)

[**AgpReleasePhysical**](nc-videoagp-pagp_release_physical.md)

[**AgpReserveVirtual**](nc-videoagp-pagp_reserve_virtual.md)
