---
UID: NC:d3d10umddi.PFND3D10DDI_DRAWAUTO
title: PFND3D10DDI_DRAWAUTO
author: windows-driver-content
description: The DrawAuto function works similarly to the Draw function, except DrawAuto is used for the special case where vertex data is written through the stream-output unit and then recycled as a vertex buffer.
old-location: display\drawauto.htm
old-project: display
ms.assetid: 83d96dc0-dfd4-449e-9e14-18f354d44534
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DrawAuto, DrawAuto callback function [Display Devices], PFND3D10DDI_DRAWAUTO, PFND3D10DDI_DRAWAUTO callback, UserModeDisplayDriverDx10_Functions_ff0a6fae-2ed9-4b49-8095-fe5f61cac148.xml, d3d10umddi/DrawAuto, display.drawauto
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
-	DrawAuto
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3D10DDI_DRAWAUTO callback function


## -description


The <b>DrawAuto</b> function works similarly to the <a href="https://msdn.microsoft.com/7a6f1d56-12be-4185-97bf-06f265ee6fe3">Draw</a> function, except <b>DrawAuto</b> is used for the special case where vertex data is written through the stream-output unit and then recycled as a vertex buffer. The driver determines the number of primitives, in part, by how much data was written to the buffer through stream output. 


## -parameters




### -param Arg1








#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DrawAuto</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

