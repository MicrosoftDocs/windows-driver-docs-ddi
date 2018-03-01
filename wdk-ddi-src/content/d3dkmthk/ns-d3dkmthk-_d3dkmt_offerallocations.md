---
UID: NS:d3dkmthk._D3DKMT_OFFERALLOCATIONS
title: "_D3DKMT_OFFERALLOCATIONS"
author: windows-driver-content
description: Defines the video memory allocations that the driver offers for reuse. Used with the D3DKMTOfferAllocations function.
old-location: display\d3dkmt_offerallocations.htm
old-project: display
ms.assetid: 6f6df55d-bb23-4a70-97f4-32809d1a41a5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_OFFERALLOCATIONS, D3DKMT_OFFERALLOCATIONS structure [Display Devices], _D3DKMT_OFFERALLOCATIONS, d3dkmthk/D3DKMT_OFFERALLOCATIONS, display.d3dkmt_offerallocations
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	D3dkmthk.h
api_name:
-	D3DKMT_OFFERALLOCATIONS
product: Windows
targetos: Windows
req.typenames: D3DKMT_OFFERALLOCATIONS
---

# _D3DKMT_OFFERALLOCATIONS structure


## -description


Defines the video memory allocations that the driver offers for reuse. Used with the  <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_offerallocations.md">D3DKMTOfferAllocations</a>  function.


## -syntax


````
typedef struct _D3DKMT_OFFERALLOCATIONS {
  D3DKMT_HANDLE         hDevice;
  D3DKMT_HANDLE         *pResources;
  const D3DKMT_HANDLE   *HandleList;
  UINT                  NumAllocations;
  D3DKMT_OFFER_PRIORITY Priority;
} D3DKMT_OFFERALLOCATIONS;
````


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that created the allocations.


### -field pResources

[in] An array of Direct3D runtime handles to resources to offer.

If the user-mode driver uses the array specified by <b>HandleList</b> to offer a list of allocations, it must set <b>pResources</b> to <b>NULL</b>. Conversely, if the driver uses the array specified by <b>pResources</b> to offer a list of resources, it must set <b>HandleList</b> to <b>NULL</b>.


### -field HandleList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to allocations to offer.

If resources were created with the <b>D3D10_DDI_BIND_PRESENT</b> flag value set in <i>pCreateResource</i>-&gt;<b>BindFlags</b>, offer the resources by their allocation handles, not by their resource handles.


### -field NumAllocations

[in] The number of items in the <b>pResources</b> or <b>HandleList</b> members, whichever is not <b>NULL</b>.


### -field Priority

[in] The priority, of type  <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_offer_priority.md">D3DKMT_OFFER_PRIORITY</a>, with which to offer the allocations for reuse.


### -field Flags

 




## -see-also

<a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_offerallocations.md">D3DKMTOfferAllocations</a>



<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_offer_priority.md">D3DKMT_OFFER_PRIORITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OFFERALLOCATIONS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

