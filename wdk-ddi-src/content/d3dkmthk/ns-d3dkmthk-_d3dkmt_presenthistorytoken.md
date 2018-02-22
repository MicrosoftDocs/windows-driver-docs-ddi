---
UID: NS:d3dkmthk._D3DKMT_PRESENTHISTORYTOKEN
title: "_D3DKMT_PRESENTHISTORYTOKEN"
author: windows-driver-content
description: The D3DKMT_PRESENTHISTORYTOKEN structure identifies a type of present operation.
old-location: display\d3dkmt_presenthistorytoken.htm
old-project: display
ms.assetid: d3571412-d853-496b-a651-2c8860a28e9d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_D3DKMT_PRESENTHISTORYTOKEN, OpenGL_Structs_6a454620-8217-4119-bbdd-4caa83169e27.xml, D3DKMT_PRESENTHISTORYTOKEN, D3DKMT_PRESENTHISTORYTOKEN structure [Display Devices], d3dkmthk/D3DKMT_PRESENTHISTORYTOKEN, display.d3dkmt_presenthistorytoken"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system.
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
-	d3dkmthk.h
apiname:
-	D3DKMT_PRESENTHISTORYTOKEN
product: Windows
targetos: Windows
req.typenames: D3DKMT_PRESENTHISTORYTOKEN
---

# _D3DKMT_PRESENTHISTORYTOKEN structure


## -description


The D3DKMT_PRESENTHISTORYTOKEN structure identifies a type of present operation. 


## -syntax


````
typedef struct _D3DKMT_PRESENTHISTORYTOKEN {
  D3DKMT_PRESENT_MODEL Model;
  UINT                 TokenSize;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  UINT64               CompositionBindingId;
#endif 
  union {
    D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN       Flip;
    D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN        Blt;
    D3DKMT_VISTABLTMODEL_PRESENTHISTORYTOKEN   VistaBlt;
    D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN        Gdi;
    D3DKMT_FENCE_PRESENTHISTORYTOKEN           Fence;
    D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN GdiSysMem;
    D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN     Composition;
  } Token;
} D3DKMT_PRESENTHISTORYTOKEN;
````


## -struct-fields




### -field Model

[in] A <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_present_model.md">D3DKMT_PRESENT_MODEL</a>-typed value that indicates the model for a present operation. 


### -field TokenSize

[in] The size, in bytes, of the present history token including the value in the <b>Model</b> member. When you submit a token, you should set <b>TokenSize</b> to zero. When the ICD calls <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetpresenthistory.md">D3DKMTGetPresentHistory</a> to retrieve present history, the runtime initializes <b>TokenSize</b>. You can then use the value in <b>TokenSize</b> to go to the next token in the present-history buffer. 

A <i>present history token</i> is a data packet that the rendering app submits to inform the Desktop Window Manager (DWM) that rendering is complete and the swap chain back buffer is ready to be presented.


### -field CompositionBindingId

The identifer of the active bound buffer of the composition surface.

Supported starting with Windows 8.


### -field Token



#### Flip

[in/out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_flipmodel_presenthistorytoken.md">D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN</a> structure that identifies a flip present-history operation. The <b>Token</b> union that is contained in D3DKMT_PRESENTHISTORYTOKEN holds this structure if the <b>Model</b> member is D3DKMT_PM_REDIRECTED_FLIP. 



#### Blt

[in/out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_bltmodel_presenthistorytoken.md">D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN</a> structure that identifies a bit-block transfer (bitblt) present-history operation. The union that is contained in D3DKMT_PRESENTHISTORYTOKEN holds a structure of this type if the <b>Model</b> member is D3DKMT_PM_REDIRECTED_BLT. 



#### VistaBlt

[in/out] A <b>ULONGLONG</b> value that identifies a Windows Vista bit-block transfer (bitblt) present-history operation. The union that is contained in D3DKMT_PRESENTHISTORYTOKEN holds a value of this type if the <b>Model</b> member is D3DKMT_PM_REDIRECTED_VISTABLT. 



#### Gdi

[in/out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_gdimodel_presenthistorytoken.md">D3DKMT_GDIMODEL_PRESENTHISTORYTOKEN</a> structure that identifies a GDI present-history operation. The union that is contained in D3DKMT_PRESENTHISTORYTOKEN holds a structure of this type if the <b>Model</b> member is D3DKMT_PM_REDIRECTED_GDI. 



#### Fence

[in/out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_fence_presenthistorytoken.md">D3DKMT_FENCE_PRESENTHISTORYTOKEN</a> structure that identifies a fence present-history operation. The union that is contained in D3DKMT_PRESENTHISTORYTOKEN holds a structure of this type if the <b>Model</b> member is D3DKMT_PM_SCREENCAPTUREFENCE. 



#### GdiSysMem

[in/out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_gdimodel_sysmem_presenthistorytoken.md">D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN</a> structure that identifies a GDI system present-history operation. The union that is contained in D3DKMT_PRESENTHISTORYTOKEN holds a structure of this type if the <b>Model</b> member is D3DKMT_PM_REDIRECTED_GDI_SYSMEM.



#### Composition

[in/out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_composition_presenthistorytoken.md">D3DKMT_COMPOSITION_PRESENTHISTORYTOKEN</a> structure that identifies a composition swap chain present-history operation. This type of presentation is used for XAML-based apps.

Supported starting with Windows 8.1.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_fence_presenthistorytoken.md">D3DKMT_FENCE_PRESENTHISTORYTOKEN</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_bltmodel_presenthistorytoken.md">D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_gdimodel_sysmem_presenthistorytoken.md">D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN</a>



<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_present_model.md">D3DKMT_PRESENT_MODEL</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_flipmodel_presenthistorytoken.md">D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN</a>



<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_present_model.md">D3DKMT_PRESENT_MODEL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_PRESENTHISTORYTOKEN structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

