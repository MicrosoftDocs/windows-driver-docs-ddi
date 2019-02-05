---
UID: NS:video._VP_SCATTER_GATHER_ELEMENT
title: _VP_SCATTER_GATHER_ELEMENT (video.h)
description: The VP_SCATTER_GATHER_ELEMENT structure is used to store information about a single scatter/gather element.
old-location: display\vp_scatter_gather_element.htm
tech.root: display
ms.assetid: 7b0ca123-8847-4dc3-b0f5-9788104381ec
ms.date: 05/10/2018
ms.keywords: "*PVP_SCATTER_GATHER_ELEMENT, PVP_SCATTER_GATHER_ELEMENT, PVP_SCATTER_GATHER_ELEMENT structure pointer [Display Devices], VP_SCATTER_GATHER_ELEMENT, VP_SCATTER_GATHER_ELEMENT structure [Display Devices], Video_Structs_eacc94d7-8de2-4847-b843-3ae56bbca6d5.xml, _VP_SCATTER_GATHER_ELEMENT, display.vp_scatter_gather_element, video/PVP_SCATTER_GATHER_ELEMENT, video/VP_SCATTER_GATHER_ELEMENT"
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	video.h
api_name:
-	VP_SCATTER_GATHER_ELEMENT
product:
- Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_ELEMENT, *PVP_SCATTER_GATHER_ELEMENT
---

# _VP_SCATTER_GATHER_ELEMENT structure


## -description


The VP_SCATTER_GATHER_ELEMENT structure is used to store information about a single scatter/gather element.


## -struct-fields




### -field Address

Specifies the logical address of one scatter/gather element.


### -field Length

Specifies the length, in bytes, of the scatter/gather element.


### -field Reserved

Reserved for system use.


## -remarks



This structure is available in Windows XP and later.

A VP_SCATTER_GATHER_ELEMENT structure is one element of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570572">VP_SCATTER_GATHER_LIST</a> structure's array member.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570572">VP_SCATTER_GATHER_LIST</a>
 

 

