---
UID: NS:d3d10umddi.D3D11DDIARG_BUFFER_RENDERTARGETVIEW
title: D3D11DDIARG_BUFFER_RENDERTARGETVIEW
author: windows-driver-content
description: The D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure describes a buffer that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d11ddiarg_buffer_rendertargetview.htm
old-project: display
ms.assetid: 1c89b4bd-7473-4da6-afbe-4103f3f3d7be
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_BUFFER_RENDERTARGETVIEW
---

# D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure


## -description


The D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure describes a buffer that is used to create a render target view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a> function. 


## -syntax


````
typedef struct D3D11DDIARG_BUFFER_RENDERTARGETVIEW {
  union {
    UINT FirstElement;
    UINT ElementOffset;
  };
  union {
    UINT NumElements;
    UINT ElementWidth;
  };
} D3D11DDIARG_BUFFER_RENDERTARGETVIEW;
````


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

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createrendertargetview.md">D3D10DDIARG_CREATERENDERTARGETVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_BUFFER_RENDERTARGETVIEW structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

