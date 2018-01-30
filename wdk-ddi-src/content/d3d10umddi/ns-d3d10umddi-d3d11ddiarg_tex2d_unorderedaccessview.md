---
UID: NS:d3d10umddi.D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW
title: D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW
author: windows-driver-content
description: The D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW structure describes a two-dimensional texture (2-D) that is used to create an unordered access view in a call to the CreateUnorderedAccessView function.
old-location: display\d3d11ddiarg_tex2d_unorderedaccessview.htm
old-project: display
ms.assetid: 2d6a5945-5e30-404c-8ddb-13be781da1b4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW, D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW structure [Display Devices], D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW, display.d3d11ddiarg_tex2d_unorderedaccessview, UMDisplayDriver_Dx11param_Structs_ca281413-3ae7-472c-acd6-76c8ef97b713.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system.
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
-	D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW
---

# D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW structure


## -description


The D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW structure describes a two-dimensional texture (2-D) that is used to create an unordered access view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a> function. 


## -syntax


````
typedef struct D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW {
  UINT MipSlice;
  UINT FirstArraySlice;
  UINT ArraySize;
} D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW;
````


## -struct-fields




### -field MipSlice

[in] The identifier of the MIP-map slice. 


### -field FirstArraySlice

[in] The identifier of the first array slice. 


### -field ArraySize

[in] The number of array slices for the texture. 


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview.md">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize.md">CalcPrivateUnorderedAccessViewSize</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

