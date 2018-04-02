---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_COPYTILES
title: PFND3DWDDM1_3DDI_COPYTILES
author: windows-driver-content
description: Copies tiles from buffer to tiled resource or vice versa.
old-location: display\copytiles.htm
old-project: display
ms.assetid: 8DA0FF6C-CA2C-4943-93C3-BFC3773617CC
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CopyTiles, CopyTiles callback function [Display Devices], PFND3DWDDM1_3DDI_COPYTILES, d3d10umddi/CopyTiles, display.copytiles
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
-	CopyTiles
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3DWDDM1_3DDI_COPYTILES callback


## -description


Copies tiles from buffer to tiled resource or vice versa.


## -parameters




### -param hDevice

A handle to the display device (graphics context).


### -param hTiledResource

A handle to the tiled resource.


### -param *pTileRegionStartCoord [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn440996">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the destination tiled resource.


### -param *pTileRegionSize [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn440997">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structure that describes the size of the tiled region.


### -param hBuffer

A handle to a resource that represents a default, dynamic, or staging buffer.


### -param BufferStartOffsetInBytes

The offset, in bytes, into the buffer at <i>hBuffer</i> to start the operation.


### -param Flags

A combination of <a href="https://msdn.microsoft.com/library/windows/hardware/dn458989">D3DWDDM1_3DDI_TILE_COPY_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code.

The Direct3D runtime does not expect this function to fail.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn440996">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn458989">D3DWDDM1_3DDI_TILE_COPY_FLAG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn440997">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

