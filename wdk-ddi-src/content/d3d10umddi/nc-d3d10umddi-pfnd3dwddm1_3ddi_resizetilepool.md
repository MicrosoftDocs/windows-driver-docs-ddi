---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_RESIZETILEPOOL
title: PFND3DWDDM1_3DDI_RESIZETILEPOOL
author: windows-driver-content
description: Resizes a tile pool.
old-location: display\resizetilepool.htm
old-project: display
ms.assetid: 184EF418-1B1E-4A10-8F10-1331DF99DCBD
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.resizetilepool, ResizeTilePool callback function [Display Devices], ResizeTilePool, PFND3DWDDM1_3DDI_RESIZETILEPOOL, PFND3DWDDM1_3DDI_RESIZETILEPOOL, d3d10umddi/ResizeTilePool
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
-	ResizeTilePool
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3DWDDM1_3DDI_RESIZETILEPOOL callback


## -description


Resizes a tile pool.




## -prototype


````
PFND3DWDDM1_3DDI_RESIZETILEPOOL ResizeTilePool;

VOID APIENTRY* ResizeTilePool(
   D3D10DDI_HDEVICE   hDevice,
   D3D10DDI_HRESOURCE hTilePool,
   UINT64             NewSizeInBytes
)
{ ... }
````


## -parameters




#### - hDevice

A handle to the display device (graphics context).


#### - hTilePool

A handle to the tile pool to resize.


#### - NewSizeInBytes

The new size, in bytes, of the tile pool. The size must be a multiple of 64 KB or zero.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. Returns <b>S_OK</b> if successful; otherwise, returns one of the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The new tile pool size isn't a multiple of 64 KB or zero. The existing tile pool remains unchanged, which includes existing mappings.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The driver had to allocate space for new page table mappings but ran out of memory. The existing tile pool remains unchanged, which includes existing mappings.

</td>
</tr>
</table> 

The Direct3D runtime performs minimal validation of parameters, but it will fail the call if the new tile pool size isn't a multiple of the tile size, or zero.


