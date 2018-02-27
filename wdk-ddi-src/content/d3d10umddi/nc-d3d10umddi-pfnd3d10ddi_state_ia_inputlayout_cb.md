---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB
title: PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB
author: windows-driver-content
description: The pfnStateIaInputLayoutCb function causes the Microsoft Direct3D 10 runtime to refresh the input layout state.
old-location: display\pfnstateiainputlayoutcb.htm
old-project: display
ms.assetid: fce49c60-8573-4a28-9d1c-5cf33d260db3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB, d3d10state_functions_7b16723d-2341-4413-9a3c-e1755e34b55e.xml, d3d10umddi/pfnStateIaInputLayoutCb, display.pfnstateiainputlayoutcb, pfnStateIaInputLayoutCb, pfnStateIaInputLayoutCb callback function [Display Devices]
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
-	pfnStateIaInputLayoutCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB callback


## -description


The <b>pfnStateIaInputLayoutCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the input layout state.


## -prototype


````
PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB pfnStateIaInputLayoutCb;

void APIENTRY pfnStateIaInputLayoutCb(
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

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

