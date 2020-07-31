---
UID: NC:d3d10umddi.PFND3D10DDI_DRAWAUTO
title: PFND3D10DDI_DRAWAUTO (d3d10umddi.h)
description: The DrawAuto function works similarly to the Draw function, except DrawAuto is used for the special case where vertex data is written through the stream-output unit and then recycled as a vertex buffer.
old-location: display\drawauto.htm
ms.assetid: 83d96dc0-dfd4-449e-9e14-18f354d44534
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_DRAWAUTO callback function"]
ms.keywords: DrawAuto, DrawAuto callback function [Display Devices], PFND3D10DDI_DRAWAUTO, PFND3D10DDI_DRAWAUTO callback, UserModeDisplayDriverDx10_Functions_ff0a6fae-2ed9-4b49-8095-fe5f61cac148.xml, d3d10umddi/DrawAuto, display.drawauto
f1_keywords:
 - "d3d10umddi/DrawAuto"
 - "DrawAuto"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- DrawAuto
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_DRAWAUTO callback function


## -description


The <b>DrawAuto</b> function works similarly to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_draw">Draw</a> function, except <b>DrawAuto</b> is used for the special case where vertex data is written through the stream-output unit and then recycled as a vertex buffer. The driver determines the number of primitives, in part, by how much data was written to the buffer through stream output. 


## -parameters




### -param Arg1


*hDevice* [in]

A handle to the display device (graphics context).




## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DrawAuto</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

