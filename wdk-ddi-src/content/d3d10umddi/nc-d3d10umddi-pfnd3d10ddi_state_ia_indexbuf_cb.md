---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_IA_INDEXBUF_CB
title: PFND3D10DDI_STATE_IA_INDEXBUF_CB
author: windows-driver-content
description: The pfnStateIaIndexBufCb function causes the Microsoft Direct3D 10 runtime to refresh the index buffer state.
old-location: display\pfnstateiaindexbufcb.htm
old-project: display
ms.assetid: 3925bf83-1900-4d88-8100-1ecaa952dead
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnstateiaindexbufcb, pfnStateIaIndexBufCb callback function [Display Devices], pfnStateIaIndexBufCb, PFND3D10DDI_STATE_IA_INDEXBUF_CB, PFND3D10DDI_STATE_IA_INDEXBUF_CB, d3d10umddi/pfnStateIaIndexBufCb, d3d10state_functions_0bf4b875-3cd1-4a62-a8b5-4dd61259188b.xml
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
-	pfnStateIaIndexBufCb
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---

# PFND3D10DDI_STATE_IA_INDEXBUF_CB callback


## -description


The <b>pfnStateIaIndexBufCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the index buffer state.


## -prototype


````
PFND3D10DDI_STATE_IA_INDEXBUF_CB pfnStateIaIndexBufCb;

void APIENTRY pfnStateIaIndexBufCb(
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



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_IA_INDEXBUF_CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

