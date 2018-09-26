---
UID: NC:d3d10umddi.PFND3D10DDI_DRAWINDEXED
title: PFND3D10DDI_DRAWINDEXED
author: windows-driver-content
description: The DrawIndexed function draws indexed primitives.
old-location: display\drawindexed.htm
ms.assetid: d1097bb6-35ac-4069-ae05-b74c75a98e21
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DrawIndexed, DrawIndexed callback function [Display Devices], PFND3D10DDI_DRAWINDEXED, PFND3D10DDI_DRAWINDEXED callback, UserModeDisplayDriverDx10_Functions_4529cc06-0ad4-41ea-8cab-b55a398cb889.xml, d3d10umddi/DrawIndexed, display.drawindexed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	DrawIndexed
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_DRAWINDEXED callback function


## -description


The <b>DrawIndexed</b> function draws indexed primitives.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*StartIndexLocation* [in]

The first index in the index buffer that indexes are read from to draw the primitives.

### -param Arg3

*BaseVertexLocation* [in]

The number that should be added to each index that is referenced by the various primitives to determine the actual index of the vertex elements in each vertex stream.

### -param Arg4

*IndexCount* [in]

The number of indexes in the index buffer that indexes are read from to draw the primitives.




## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DrawIndexed</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

