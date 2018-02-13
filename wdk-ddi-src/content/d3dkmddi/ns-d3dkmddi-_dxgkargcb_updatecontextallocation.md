---
UID: NS:d3dkmddi._DXGKARGCB_UPDATECONTEXTALLOCATION
title: "_DXGKARGCB_UPDATECONTEXTALLOCATION"
author: windows-driver-content
description: DXGKARGCB_UPDATECONTEXTALLOCATION contains the data used to call DxgkCbUpdateContextAllocation.
old-location: display\dxgkargcb_updatecontextallocation.htm
old-project: display
ms.assetid: 07BFCA6C-4E75-4BB5-9F6A-22E1FFAFFF6F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGKARGCB_UPDATECONTEXTALLOCATION, display.dxgkargcb_updatecontextallocation, DXGKARGCB_UPDATECONTEXTALLOCATION structure [Display Devices], DXGKARGCB_UPDATECONTEXTALLOCATION, d3dkmddi/DXGKARGCB_UPDATECONTEXTALLOCATION"
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
-	DXGKARGCB_UPDATECONTEXTALLOCATION
product: Windows
targetos: Windows
req.typenames: DXGKARGCB_UPDATECONTEXTALLOCATION
---

# _DXGKARGCB_UPDATECONTEXTALLOCATION structure


## -description


<b>DXGKARGCB_UPDATECONTEXTALLOCATION</b> contains the data used to call <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_updatecontextallocation.md">DxgkCbUpdateContextAllocation</a>.


## -syntax


````
typedef struct _DXGKARGCB_UPDATECONTEXTALLOCATION {
  HANDLE hAllocation;
  PVOID  pPrivateDriverData;
  UINT   PrivateDriverDataSize;
} DXGKARGCB_UPDATECONTEXTALLOCATION;
````


## -struct-fields




### -field hAllocation

Handle to the context allocation being updated. The allocation defines a physical adapter in a linked display adapter link.


### -field pPrivateDriverData

Pointer to a private driver data buffer to be passed to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_updatecontextallocation.md">DxgkCbUpdateContextAllocation</a> paging operation.


### -field PrivateDriverDataSize

Specify the size of the driver private data.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_updatecontextallocation.md">DxgkCbUpdateContextAllocation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARGCB_UPDATECONTEXTALLOCATION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

