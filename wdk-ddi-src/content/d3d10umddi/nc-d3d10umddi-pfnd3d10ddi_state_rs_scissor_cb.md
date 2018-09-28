---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_RS_SCISSOR_CB
title: PFND3D10DDI_STATE_RS_SCISSOR_CB
author: windows-driver-content
description: The pfnStateRsScissorCb function causes the Microsoft Direct3D 10 runtime to refresh the scissor state.
old-location: display\pfnstatersscissorcb.htm
ms.assetid: 4bb88e3c-2309-42f5-bc22-4c7182358e6e
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D10DDI_STATE_RS_SCISSOR_CB, PFND3D10DDI_STATE_RS_SCISSOR_CB callback, d3d10state_functions_8690a3ee-bc2c-4164-808b-c308a1784893.xml, d3d10umddi/pfnStateRsScissorCb, display.pfnstatersscissorcb, pfnStateRsScissorCb, pfnStateRsScissorCb callback function [Display Devices]
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
-	pfnStateRsScissorCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_RS_SCISSOR_CB callback function


## -description


The <b>pfnStateRsScissorCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the scissor state.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 


## -returns



None




## -remarks



The <b>pfnStateRsScissorCb</b> function calls the user-mode display driver's <a href="https://msdn.microsoft.com/ef61f50b-a82b-43df-865f-2f9d9ca906d4">SetScissorRects</a> function with all of the currently set scissor rectangles (that is, portions of render targets that rendering is confined to).




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541820">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/ef61f50b-a82b-43df-865f-2f9d9ca906d4">SetScissorRects</a>
 

 

