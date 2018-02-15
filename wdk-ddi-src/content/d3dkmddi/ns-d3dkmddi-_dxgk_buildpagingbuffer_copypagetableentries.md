---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES
title: "_DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES"
author: windows-driver-content
description: DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES describes the operation used copy page table entries from one location to another.
old-location: display\dxgk_buildpagingbuffer_copypagetableentries.htm
old-project: display
ms.assetid: 627FB3E6-3C5D-4104-B129-08D3EC0B963E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES structure [Display Devices], display.dxgk_buildpagingbuffer_copypagetableentries, DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES, _DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES, d3dkmddi/DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES
product: Windows
targetos: Windows
req.typenames: DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES
---

# _DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES structure


## -description


<b>DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES</b> describes the operation used copy page table entries from one location to another. 


## -syntax


````
typedef struct _DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES {
  UINT                              NumRanges;
  DXGK_BUILDPAGINGBUFFER_COPY_RANGE *pRanges;
} DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES;
````


## -struct-fields




### -field NumRanges

The number of elements in the <b>pRanges</b> array.


### -field pRanges

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_copy_range.md">DXGK_BUILDPAGINGBUFFER_COPY_RANGE</a> structure describing each range of page table entries to copy.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_copy_range.md">DXGK_BUILDPAGINGBUFFER_COPY_RANGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

