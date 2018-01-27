---
UID: NC:d3d10umddi.PFND3D10DDI_DRAWAUTO
title: PFND3D10DDI_DRAWAUTO
author: windows-driver-content
description: The DrawAuto function works similarly to the Draw function, except DrawAuto is used for the special case where vertex data is written through the stream-output unit and then recycled as a vertex buffer.
old-location: display\drawauto.htm
old-project: display
ms.assetid: 83d96dc0-dfd4-449e-9e14-18f354d44534
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.drawauto, DrawAuto callback function [Display Devices], DrawAuto, PFND3D10DDI_DRAWAUTO, PFND3D10DDI_DRAWAUTO, d3d10umddi/DrawAuto, UserModeDisplayDriverDx10_Functions_ff0a6fae-2ed9-4b49-8095-fe5f61cac148.xml
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	d3d10umddi.h
apiname: 
-	DrawAuto
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D10DDI_DRAWAUTO callback


## -description


The <b>DrawAuto</b> function works similarly to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_draw.md">Draw</a> function, except <b>DrawAuto</b> is used for the special case where vertex data is written through the stream-output unit and then recycled as a vertex buffer. The driver determines the number of primitives, in part, by how much data was written to the buffer through stream output. 


## -prototype


````
PFND3D10DDI_DRAWAUTO DrawAuto;

VOID APIENTRY DrawAuto(
  _In_ D3D10DDI_HDEVICE hDevice
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE






#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.



## -remarks


The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DrawAuto</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_DRAWAUTO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

