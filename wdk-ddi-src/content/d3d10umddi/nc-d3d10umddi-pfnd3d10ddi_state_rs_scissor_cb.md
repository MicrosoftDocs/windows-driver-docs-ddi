---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_RS_SCISSOR_CB
title: PFND3D10DDI_STATE_RS_SCISSOR_CB
author: windows-driver-content
description: The pfnStateRsScissorCb function causes the Microsoft Direct3D 10 runtime to refresh the scissor state.
old-location: display\pfnstatersscissorcb.htm
old-project: display
ms.assetid: 4bb88e3c-2309-42f5-bc22-4c7182358e6e
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3D10DDI_STATE_RS_SCISSOR_CB, d3d10state_functions_8690a3ee-bc2c-4164-808b-c308a1784893.xml, d3d10umddi/pfnStateRsScissorCb, display.pfnstatersscissorcb, pfnStateRsScissorCb, pfnStateRsScissorCb callback function [Display Devices]
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
-	pfnStateRsScissorCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_STATE_RS_SCISSOR_CB callback


## -description


The <b>pfnStateRsScissorCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the scissor state.


## -prototype


````
PFND3D10DDI_STATE_RS_SCISSOR_CB pfnStateRsScissorCb;

void APIENTRY pfnStateRsScissorCb(
  _In_ D3D10DDI_HRTCORELAYER hRuntimeDevice
)
{ ... }
````


## -parameters




### -param D3D10DDI_HRTCORELAYER








#### - hRuntimeDevice [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function. 


## -returns



None




## -remarks



The <b>pfnStateRsScissorCb</b> function calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setscissorrects.md">SetScissorRects</a> function with all of the currently set scissor rectangles (that is, portions of render targets that rendering is confined to).




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setscissorrects.md">SetScissorRects</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_RS_SCISSOR_CB callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

