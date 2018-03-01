---
UID: NS:d3dukmdt._D3DDDI_ALLOCATIONLIST
title: "_D3DDDI_ALLOCATIONLIST"
author: windows-driver-content
description: The D3DDDI_ALLOCATIONLIST structure describes information about an allocation specification that is used in direct memory access (DMA) buffering.
old-location: display\d3dddi_allocationlist.htm
old-project: display
ms.assetid: 167ceb16-d7b9-4657-84cd-f3b9de5e5267
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_ALLOCATIONLIST, D3DDDI_ALLOCATIONLIST structure [Display Devices], D3D_other_Structs_0e766b30-b39d-4107-8739-0b9290e7d489.xml, _D3DDDI_ALLOCATIONLIST, d3dukmdt/D3DDDI_ALLOCATIONLIST, display.d3dddi_allocationlist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	d3dukmdt.h
api_name:
-	D3DDDI_ALLOCATIONLIST
product: Windows
targetos: Windows
req.typenames: D3DDDI_ALLOCATIONLIST
---

# _D3DDDI_ALLOCATIONLIST structure


## -description


The <b>D3DDDI_ALLOCATIONLIST</b> structure describes information about an allocation specification that is used in direct memory access (DMA) buffering.


## -syntax


````
typedef struct _D3DDDI_ALLOCATIONLIST {
  D3DKMT_HANDLE hAllocation;
  union {
    struct {
      UINT WriteOperation  :1;
      UINT DoNotRetireInstance  :1;
#if ((DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8) || \
     (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN8))

      UINT OfferPriority  :3;
#else 
      UINT Reserved  :27;
#endif 
      UINT Reserved  :30;
    };
    UINT Value;
  };
} D3DDDI_ALLOCATIONLIST;
````


## -struct-fields




### -field hAllocation

[in] The allocation handle returned by the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenresource.md">D3DKMTOpenResource</a> function in the <b>hAllocation</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_openallocationinfo.md">D3DDDI_OPENALLOCATIONINFO</a>   structure, or by the <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createallocation.md">D3DKMTCreateAllocation</a> function in the <b>hAllocation</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a> structure.


### -field WriteOperation

[in] A UINT that can hold information about whether the allocation can be written to. Setting to 1 indicates the allocation can be written to.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field DoNotRetireInstance

[in] A UINT that can hold information about whether the allocation can be retired. Setting to 1 indicates that the video memory manager should not retire the instance of the allocation because the driver will reference it again in a subsequent DMA buffer (for example, a manual broadcast of a DMA buffer to multiple contexts). All instances of an allocation are eventually retired. This flag is rarely used.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field OfferPriority

[in] A value from the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_offer_priority.md">D3DDDI_OFFER_PRIORITY</a> enumeration that indicates the importance of video memory resources  that the user-mode display driver offers for reuse.

If <b>OfferPriority</b> does not have a value of <b>D3DDDI_OFFER_PRIORITY_NONE</b>, the allocation is considered to be offered after the DMA buffer is processed.

Setting this member is equivalent to setting bits 3 through 5 of the 32-bit <b>Value</b> member (0x0000001C).

Supported starting with Windows 8.


### -field Reserved

[in] This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 27 bits (0xFFFFFFE0) of the 32-bit <b>Value</b> member to zeros. 

Supported starting with Windows 8.

[in] This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros. 


#### - Value

[in] A 32-bit value that identifies information about an allocation specification used in DMA buffering.


## -see-also

<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_offer_priority.md">D3DDDI_OFFER_PRIORITY</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_ALLOCATIONLIST structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

