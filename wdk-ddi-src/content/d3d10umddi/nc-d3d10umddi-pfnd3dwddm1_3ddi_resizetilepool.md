---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_RESIZETILEPOOL
title: PFND3DWDDM1_3DDI_RESIZETILEPOOL
author: windows-driver-content
description: Resizes a tile pool.
old-location: display\resizetilepool.htm
tech.root: display
ms.assetid: 184EF418-1B1E-4A10-8F10-1331DF99DCBD
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DWDDM1_3DDI_RESIZETILEPOOL, PFND3DWDDM1_3DDI_RESIZETILEPOOL callback, ResizeTilePool, ResizeTilePool callback function [Display Devices], d3d10umddi/ResizeTilePool, display.resizetilepool
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	ResizeTilePool
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DWDDM1_3DDI_RESIZETILEPOOL callback function


## -description


Resizes a tile pool.




## -parameters




### -param hDevice

A handle to the display device (graphics context).


### -param hTilePool

A handle to the tile pool to resize.


### -param NewSizeInBytes

The new size, in bytes, of the tile pool. The size must be a multiple of 64 KB or zero.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. Returns <b>S_OK</b> if successful; otherwise, returns one of the following:

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



