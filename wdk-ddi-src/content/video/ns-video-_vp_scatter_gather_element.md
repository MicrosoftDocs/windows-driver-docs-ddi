---
UID: NS:video._VP_SCATTER_GATHER_ELEMENT
title: "_VP_SCATTER_GATHER_ELEMENT"
author: windows-driver-content
description: The VP_SCATTER_GATHER_ELEMENT structure is used to store information about a single scatter/gather element.
old-location: display\vp_scatter_gather_element.htm
old-project: display
ms.assetid: 7b0ca123-8847-4dc3-b0f5-9788104381ec
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VP_SCATTER_GATHER_ELEMENT, PVP_SCATTER_GATHER_ELEMENT, *PVP_SCATTER_GATHER_ELEMENT, display.vp_scatter_gather_element, PVP_SCATTER_GATHER_ELEMENT structure pointer [Display Devices], video/VP_SCATTER_GATHER_ELEMENT, VP_SCATTER_GATHER_ELEMENT structure [Display Devices], _VP_SCATTER_GATHER_ELEMENT, video/PVP_SCATTER_GATHER_ELEMENT, Video_Structs_eacc94d7-8de2-4847-b843-3ae56bbca6d5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	video.h
apiname:
-	VP_SCATTER_GATHER_ELEMENT
product: Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_ELEMENT, *PVP_SCATTER_GATHER_ELEMENT
req.product: Windows 10 or later.
---

# _VP_SCATTER_GATHER_ELEMENT structure


## -description


The VP_SCATTER_GATHER_ELEMENT structure is used to store information about a single scatter/gather element.


## -syntax


````
typedef struct _VP_SCATTER_GATHER_ELEMENT {
  PHYSICAL_ADDRESS Address;
  ULONG            Length;
  ULONG_PTR        Reserved;
} VP_SCATTER_GATHER_ELEMENT, *PVP_SCATTER_GATHER_ELEMENT;
````


## -struct-fields




### -field Address

Specifies the logical address of one scatter/gather element.


### -field Length

Specifies the length, in bytes, of the scatter/gather element.


### -field Reserved

Reserved for system use.


## -remarks



This structure is available in Windows XP and later.

A VP_SCATTER_GATHER_ELEMENT structure is one element of the <a href="..\video\ns-video-_vp_scatter_gather_list.md">VP_SCATTER_GATHER_LIST</a> structure's array member.




## -see-also

<a href="..\video\ns-video-_vp_scatter_gather_list.md">VP_SCATTER_GATHER_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VP_SCATTER_GATHER_ELEMENT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

