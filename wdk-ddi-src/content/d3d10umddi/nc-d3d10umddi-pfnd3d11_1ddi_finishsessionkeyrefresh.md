---
UID: NC:d3d10umddi.PFND3D11_1DDI_FINISHSESSIONKEYREFRESH
title: PFND3D11_1DDI_FINISHSESSIONKEYREFRESH (d3d10umddi.h)
description: Completes the switch to a new session key.
old-location: display\finishsessionkeyrefresh1.htm
ms.assetid: 95c0433f-e4da-4566-b128-34cb758b8001
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_FINISHSESSIONKEYREFRESH, PFND3D11_1DDI_FINISHSESSIONKEYREFRESH callback, d3d10umddi/pfnFinishSessionKeyRefresh, display.finishsessionkeyrefresh1, pfnFinishSessionKeyRefresh, pfnFinishSessionKeyRefresh callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnFinishSessionKeyRefresh"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3d10umddi.h
api_name:
- pfnFinishSessionKeyRefresh
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_FINISHSESSIONKEYREFRESH callback function


## -description


Completes the switch to a new session key.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCryptoSession [in]

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>.


## -returns



This callback function does not return a value.




## -remarks



<b>FinishSessionKeyRefresh</b> indicates that all buffers from that point in time will use the updated session key value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>
 

 

