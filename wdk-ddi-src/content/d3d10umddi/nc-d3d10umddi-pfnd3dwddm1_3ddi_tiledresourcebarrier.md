---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER
title: PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER
author: windows-driver-content
description: Specifies a data access ordering constraint between multiple tiled resources. For more info about this constraint, see Remarks.
old-location: display\tiledresourcebarrier.htm
old-project: display
ms.assetid: 9A2E9B3F-13E4-48D7-A3F3-E7CDCDD1E0CC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.tiledresourcebarrier, TiledResourceBarrier callback function [Display Devices], TiledResourceBarrier, PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER, PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER, d3d10umddi/TiledResourceBarrier
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	TiledResourceBarrier
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER callback


## -description


Specifies a data access ordering constraint between multiple tiled resources. For more info about this constraint, see Remarks.


## -prototype


````
PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER TiledResourceBarrier;

VOID APIENTRY* TiledResourceBarrier(
           D3D10DDI_HDEVICE    hDevice,
           D3D11DDI_HANDLETYPE TiledResourceAccessBeforeBarrierHandleType,
  _In_opt_ VOID                *hTiledResourceAccessBeforeBarrier,
           D3D11DDI_HANDLETYPE TiledResourceAccessAfterBarrierHandleType,
  _In_opt_ VOID                *hTiledResourceAccessAfterBarrier
)
{ ... }
````


## -parameters




### -param hDevice

A handle to the display device (graphics context).


### -param TiledResourceAccessBeforeBarrierHandleType

A handle to the tiled resource.


### -param *hTiledResourceAccessBeforeBarrier



### -param TiledResourceAccessAfterBarrierHandleType

The <a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_handletype.md">D3D11DDI_HANDLETYPE</a> handle type of the resources pointed to by the <i>hTiledResourceAccessBeforeBarrier</i> and <i>hTiledResourceAccessAfterBarrier</i> parameters.


### -param *hTiledResourceAccessAfterBarrier






#### - hTiledResourceAccessBeforeBarrier [in, optional]

A handle to a resource that was created with the <b>D3DWDDM1_3DDI_RESOURCE_MISC_TILED</b> flag. Access operations on this object must complete before the access operations on the object that <i>hTiledResourceAccessAfterBarrier</i> specifies.




#### - hTiledResourceAccessAfterBarrier [in, optional]

A handle to a resource that was created with the <b>D3DWDDM1_3DDI_RESOURCE_MISC_TILED</b> flag. Access operations on this object must begin after the access operations on the object that <i>hTiledResourceAccessBeforeBarrier</i> specifies.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code.

The Direct3D runtime performs minimal validation of parameters.



## -remarks


Apps can use tiled resources to reuse tiles in different resources. But a device and driver might not be able to determine whether some memory in a tile pool that was just rendered to is now being used for reading.

The Direct3D runtime calls <i>TiledResourceBarrier</i> to inform the driver that operations issued to the resource before the call must complete before any accesses that occur after the call using a different tiled resource that shares the same memory.

Either or both of the <i>hTiledResourceAccessBeforeBarrier</i> and <i>hTiledResourceAccessAfterBarrier</i> parameters (before or after the barrier) can be <b>NULL</b>. <b>NULL</b> before the barrier means that all tiled resource accesses before the barrier must complete before the resource specified after the barrier can be referenced by the GPU. <b>NULL</b> after the barrier means that any tiled resources accessed after the barrier can only be executed by the GPU after accesses to the tiled resources before the barrier are finished. If both are <b>NULL</b>, all previous tiled resource accesses must be complete before any subsequent tiled resource access can proceed.

If no calls are made to <i>TiledResourceBarrier</i>,
                     the driver can assume that accesses to different tiled resources
                     do not conflict with each other.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_handletype.md">D3D11DDI_HANDLETYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM1_3DDI_TILEDRESOURCEBARRIER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

