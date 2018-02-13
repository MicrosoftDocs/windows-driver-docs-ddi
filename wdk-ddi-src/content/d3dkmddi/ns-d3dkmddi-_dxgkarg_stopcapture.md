---
UID: NS:d3dkmddi._DXGKARG_STOPCAPTURE
title: "_DXGKARG_STOPCAPTURE"
author: windows-driver-content
description: The DXGKARG_STOPCAPTURE structure contains the handle to the allocation that is used for a capture buffer.
old-location: display\dxgkarg_stopcapture.htm
old-project: display
ms.assetid: 09b1275f-9755-44f7-ab8a-1b6797bfefde
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGKARG_STOPCAPTURE, DXGKARG_STOPCAPTURE structure [Display Devices], DXGKARG_STOPCAPTURE, display.dxgkarg_stopcapture, _DXGKARG_STOPCAPTURE, DmStructs_52028d90-8c11-425c-80ca-533664035fa5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_STOPCAPTURE
product: Windows
targetos: Windows
req.typenames: DXGKARG_STOPCAPTURE
---

# _DXGKARG_STOPCAPTURE structure


## -description


The DXGKARG_STOPCAPTURE structure contains the handle to the allocation that is used for a capture buffer.


## -syntax


````
typedef struct _DXGKARG_STOPCAPTURE {
  HANDLE hAllocation;
} DXGKARG_STOPCAPTURE;
````


## -struct-fields




### -field hAllocation

[in] A handle to the allocation that is used for a capture buffer. The display miniport driver stops the capture hardware from using the allocation.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_stopcapture.md">DxgkDdiStopCapture</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_STOPCAPTURE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

