---
UID: NS:d3d10umddi.D3D10DDIARG_BUFFER_RENDERTARGETVIEW
title: D3D10DDIARG_BUFFER_RENDERTARGETVIEW
author: windows-driver-content
description: The D3D10DDIARG_BUFFER_RENDERTARGETVIEW structure describes a buffer that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d10ddiarg_buffer_rendertargetview.htm
old-project: display
ms.assetid: 05c1d6e2-61e1-4bf0-b02e-5ea8ad144a9f
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 3, A, B, D, D3D10DDIARG_BUFFER_RENDERTARGETVIEW, D3D10DDIARG_BUFFER_RENDERTARGETVIEW structure [Display Devices], E, F, G, I, N, R, T, U, UMDisplayDriver_Dx10param_Structs_7307c354-c2a6-45e8-a9f6-9cb3d7c7724d.xml, V, W, _, d3d10umddi/D3D10DDIARG_BUFFER_RENDERTARGETVIEW, display.d3d10ddiarg_buffer_rendertargetview"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10DDIARG_BUFFER_RENDERTARGETVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_BUFFER_RENDERTARGETVIEW
---

# D3D10DDIARG_BUFFER_RENDERTARGETVIEW structure


## -description


The D3D10DDIARG_BUFFER_RENDERTARGETVIEW structure describes a buffer that is used to create a render target view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a> function. 


## -syntax


````
typedef struct D3D10DDIARG_BUFFER_RENDERTARGETVIEW {
  union {
    UINT FirstElement;
    UINT ElementOffset;
  };
  union {
    UINT NumElements;
    UINT ElementWidth;
  };
} D3D10DDIARG_BUFFER_RENDERTARGETVIEW;
````


## -struct-fields






#### - FirstElement


#### - ElementOffset

[in] The offset (that is, the number of elements) between the beginning of the buffer and the first element that is to be used in the view, starting at 0. 


#### - NumElements


#### - ElementWidth

[in] The number of elements in the view. 


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createrendertargetview.md">D3D10DDIARG_CREATERENDERTARGETVIEW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_BUFFER_RENDERTARGETVIEW structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

