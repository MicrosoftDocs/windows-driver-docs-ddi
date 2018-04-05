---
UID: NS:d3d10umddi.D3D11DDIARG_BUFFER_RENDERTARGETVIEW
title: D3D11DDIARG_BUFFER_RENDERTARGETVIEW
author: windows-driver-content
description: The D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure describes a buffer that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d11ddiarg_buffer_rendertargetview.htm
old-project: display
ms.assetid: 1c89b4bd-7473-4da6-afbe-4103f3f3d7be
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11DDIARG_BUFFER_RENDERTARGETVIEW, D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_1e10bcbc-ad5c-47b4-a36d-d1d471e38a7e.xml, d3d10umddi/D3D11DDIARG_BUFFER_RENDERTARGETVIEW, display.d3d11ddiarg_buffer_rendertargetview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_BUFFER_RENDERTARGETVIEW is supported beginning with the Windows 7 operating system.
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
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D11DDIARG_BUFFER_RENDERTARGETVIEW
product:
- Windows
targetos: Windows
req.typenames: D3D11DDIARG_BUFFER_RENDERTARGETVIEW
---

# D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure


## -description


The D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure describes a buffer that is used to create a render target view in a call to the <a href="https://msdn.microsoft.com/bf9fc732-5f9a-4fee-8ea0-19b140789463">CreateRenderTargetView</a> function. 


## -struct-fields






#### - ElementOffset

[in] The offset, in bytes, to the first element in the buffer. 


#### - ElementWidth

[in] The width, in elements, in the buffer. 


#### - FirstElement

[in] The offset, in bytes, to the first element in the buffer. 


#### - NumElements

[in] The number of elements in the buffer. 


## -see-also




<a href="https://msdn.microsoft.com/14d85e4a-960c-4438-9360-a4f2677603b8">CalcPrivateRenderTargetViewSize</a>



<a href="https://msdn.microsoft.com/bf9fc732-5f9a-4fee-8ea0-19b140789463">CreateRenderTargetView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541689">D3D10DDIARG_CREATERENDERTARGETVIEW</a>
 

 

