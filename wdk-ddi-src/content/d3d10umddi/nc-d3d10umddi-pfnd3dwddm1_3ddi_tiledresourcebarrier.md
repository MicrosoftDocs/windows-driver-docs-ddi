---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER
title: PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER (d3d10umddi.h)
description: Specifies a data access ordering constraint between multiple tiled resources. For more info about this constraint, see Remarks.
old-location: display\tiledresourcebarrier.htm
ms.assetid: 9A2E9B3F-13E4-48D7-A3F3-E7CDCDD1E0CC
ms.date: 05/10/2018
keywords: ["PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER callback function"]
ms.keywords: PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER, PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER callback, TiledResourceBarrier, TiledResourceBarrier callback function [Display Devices], d3d10umddi/TiledResourceBarrier, display.tiledresourcebarrier
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: 
f1_keywords:
 - "d3d10umddi/TiledResourceBarrier"
 - "TiledResourceBarrier"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - TiledResourceBarrier
product:
 - Windows
---

# PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER callback function

## -description

Specifies a data access ordering constraint between multiple tiled resources. For more info about this constraint, see Remarks.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param TiledResourceAccessBeforeBarrierHandleType

A handle to the tiled resource.

### -param hTiledResourceAccessBeforeBarrier

A handle to a resource that was created with the <b>D3DWDDM1_3DDI_RESOURCE_MISC_TILED</b> flag. Access operations on this object must complete before the access operations on the object that <i>hTiledResourceAccessAfterBarrier</i> specifies.

### -param TiledResourceAccessAfterBarrierHandleType

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_handletype">D3D11DDI_HANDLETYPE</a> handle type of the resources pointed to by the <i>hTiledResourceAccessBeforeBarrier</i> and <i>hTiledResourceAccessAfterBarrier</i> parameters.

### -param hTiledResourceAccessAfterBarrier

A handle to a resource that was created with the <b>D3DWDDM1_3DDI_RESOURCE_MISC_TILED</b> flag. Access operations on this object must begin after the access operations on the object that <i>hTiledResourceAccessBeforeBarrier</i> specifies.

## -remarks


The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code.

The Direct3D runtime performs minimal validation of parameters.


Apps can use tiled resources to reuse tiles in different resources. But a device and driver might not be able to determine whether some memory in a tile pool that was just rendered to is now being used for reading.

The Direct3D runtime calls <i>TiledResourceBarrier</i> to inform the driver that operations issued to the resource before the call must complete before any accesses that occur after the call using a different tiled resource that shares the same memory.

Either or both of the <i>hTiledResourceAccessBeforeBarrier</i> and <i>hTiledResourceAccessAfterBarrier</i> parameters (before or after the barrier) can be <b>NULL</b>. <b>NULL</b> before the barrier means that all tiled resource accesses before the barrier must complete before the resource specified after the barrier can be referenced by the GPU. <b>NULL</b> after the barrier means that any tiled resources accessed after the barrier can only be executed by the GPU after accesses to the tiled resources before the barrier are finished. If both are <b>NULL</b>, all previous tiled resource accesses must be complete before any subsequent tiled resource access can proceed.

If no calls are made to <i>TiledResourceBarrier</i>,
                     the driver can assume that accesses to different tiled resources
                     do not conflict with each other.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_handletype">D3D11DDI_HANDLETYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

