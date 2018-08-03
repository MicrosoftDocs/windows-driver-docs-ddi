---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB
title: PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB
author: windows-driver-content
description: The pfnStateIaInputLayoutCb function causes the Microsoft Direct3D 10 runtime to refresh the input layout state.
old-location: display\pfnstateiainputlayoutcb.htm
tech.root: display
ms.assetid: fce49c60-8573-4a28-9d1c-5cf33d260db3
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB, PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB callback, d3d10state_functions_7b16723d-2341-4413-9a3c-e1755e34b55e.xml, d3d10umddi/pfnStateIaInputLayoutCb, display.pfnstateiainputlayoutcb, pfnStateIaInputLayoutCb, pfnStateIaInputLayoutCb callback function [Display Devices]
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB callback function


## -description


The <b>pfnStateIaInputLayoutCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the input layout state.


## -parameters




### -param Arg1








#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541820">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

