---
UID: NS:d3dumddi._D3DDDIARG_OFFERRESOURCES
title: "_D3DDDIARG_OFFERRESOURCES"
author: windows-driver-content
description: Describes video memory resources that the user-mode display driver offers for reuse. Used with the OfferResources function.
old-location: display\d3dddiarg_offerresources.htm
old-project: display
ms.assetid: 3c5e5dae-14f6-47b9-8c27-48ecc73a43ef
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_OFFERRESOURCES, D3DDDIARG_OFFERRESOURCES structure [Display Devices], _D3DDDIARG_OFFERRESOURCES, d3dumddi/D3DDDIARG_OFFERRESOURCES, display.d3dddiarg_offerresources
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dumddi.h
api_name:
-	D3DDDIARG_OFFERRESOURCES
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_OFFERRESOURCES
---

# _D3DDDIARG_OFFERRESOURCES structure


## -description


 Describes video memory resources that the user-mode display driver offers for reuse. Used with the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerresources.md">OfferResources</a>  function.


## -syntax


````
typedef struct _D3DDDIARG_OFFERRESOURCES {
  const HANDLE          *pResources;
  UINT                  Resources;
  D3DDDI_OFFER_PRIORITY Priority;
} D3DDDIARG_OFFERRESOURCES;
````


## -struct-fields




### -field pResources

[in] A pointer to an array of handles to the video memory resources that the driver offers.


### -field Resources

[in] The number of elements in the array pointed to by <b>pResources</b>.


### -field Priority

[in] A value of type <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_offer_priority.md">D3DDDI_OFFER_PRIORITY</a> that indicates the importance of the resources pointed to by <b>pResources</b>.


## -remarks



This structure is pointed to by  the <i>pData</i> parameter of the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerresources.md">OfferResources</a> routine.




## -see-also

<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_offer_priority.md">D3DDDI_OFFER_PRIORITY</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerresources.md">OfferResources</a>



 

 


