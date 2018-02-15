---
UID: NS:d3dumddi._D3DDDIARG_CAPTURETOSYSMEM
title: "_D3DDDIARG_CAPTURETOSYSMEM"
author: windows-driver-content
description: The D3DDDIARG_CAPTURETOSYSMEM structure describes the parameters of a bit-block transfer (bitblt) from a capture buffer to a video memory surface.
old-location: display\d3dddiarg_capturetosysmem.htm
old-project: display
ms.assetid: 8cf42c60-655a-4deb-9351-4a3505b49593
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_param_Structs_497b7e52-066f-4078-b673-0f9cd3b6f4c1.xml, d3dumddi/D3DDDIARG_CAPTURETOSYSMEM, D3DDDIARG_CAPTURETOSYSMEM structure [Display Devices], _D3DDDIARG_CAPTURETOSYSMEM, D3DDDIARG_CAPTURETOSYSMEM, display.d3dddiarg_capturetosysmem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
apiname:
-	D3DDDIARG_CAPTURETOSYSMEM
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CAPTURETOSYSMEM
---

# _D3DDDIARG_CAPTURETOSYSMEM structure


## -description


The D3DDDIARG_CAPTURETOSYSMEM structure describes the parameters of a bit-block transfer (bitblt) from a capture buffer to a video memory surface. 


## -syntax


````
typedef struct _D3DDDIARG_CAPTURETOSYSMEM {
  HANDLE hSrcResource;
  RECT   SrcRect;
  HANDLE hDstResource;
  UINT   DstSubResourceIndex;
  RECT   DstRect;
} D3DDDIARG_CAPTURETOSYSMEM;
````


## -struct-fields




### -field hSrcResource

[in] A handle to the source resource.


### -field SrcRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure for the source rectangle. 


### -field hDstResource

[in] A handle to the destination resource.


### -field DstSubResourceIndex

[in] The index to the destination surface within the resource. 


### -field DstRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure for the destination rectangle. 


## -remarks



Because the source resource that is specified by the <b>hSrcResource</b> member is a capture buffer, it is guaranteed to be a stand alone resource. Therefore, in a call to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_capturetosysmem.md">CaptureToSysMem</a>, the Microsoft Direct3D runtime is not required to supply an index to a sub source surface within the resource. However, an index to a sub source surface is required when the runtime calls the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_blt.md">Blt</a> function to perform a more general bitblt.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_capturetosysmem.md">CaptureToSysMem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_blt.md">Blt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CAPTURETOSYSMEM structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

