---
UID: NS:d3d10umddi.D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW
title: D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW
author: windows-driver-content
description: The D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW structure describes a buffer that is used to create a shader resource view in a call to the CreateShaderResourceView(D3D11) function.
old-location: display\d3d11ddiarg_bufferex_shaderresourceview.htm
old-project: display
ms.assetid: b3585a06-fdb0-4fe9-8d5c-63680039a789
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW, d3d10umddi/D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW, UMDisplayDriver_Dx11param_Structs_49ef78b9-8a6f-4b67-bf2f-bae79086b6c7.xml, D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW structure [Display Devices], display.d3d11ddiarg_bufferex_shaderresourceview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW is supported beginning with the Windows 7 operating system.
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
-	D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW
---

# D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW structure


## -description


The D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW structure describes a buffer that is used to create a shader resource view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview.md">CreateShaderResourceView(D3D11)</a> function. 


## -syntax


````
typedef struct D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW {
  union {
    UINT FirstElement;
    UINT ElementOffset;
  };
  union {
    UINT NumElements;
    UINT ElementWidth;
  };
  UINT  Flags;
} D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW;
````


## -struct-fields




### -field FirstElement

[in] The offset, in bytes, to the first element in the buffer. 


### -field ElementOffset

[in] The offset, in bytes, to the first element in the buffer. 


### -field NumElements

[in] The number of elements in the buffer. 


### -field ElementWidth

[in] The width, in elements, in the buffer. 


### -field Flags

[in] A valid bitwise OR of flag values that describe the buffer. Currently, the Direct3D runtime supports only the D3D11_DDI_BUFFEREX_SRV_FLAG_RAW (0x00000001) flag. If this flag is set, the buffer is in raw format. 


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize(D3D11)</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createshaderresourceview.md">CreateShaderResourceView(D3D11)</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createshaderresourceview.md">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_BUFFEREX_SHADERRESOURCEVIEW structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

