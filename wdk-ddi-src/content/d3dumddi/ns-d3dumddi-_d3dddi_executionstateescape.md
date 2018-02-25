---
UID: NS:d3dumddi._D3DDDI_EXECUTIONSTATEESCAPE
title: "_D3DDDI_EXECUTIONSTATEESCAPE"
author: windows-driver-content
description: Specifies the state of the device.
old-location: display\d3dddi_executionstateescape.htm
old-project: display
ms.assetid: 9BA78743-91AA-4AAC-9FB3-CF8B30FC15AE
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, A, C, D, D3DDDI_EXECUTIONSTATEESCAPE, D3DDDI_EXECUTIONSTATEESCAPE structure [Display Devices], E, I, N, O, P, S, T, U, X, _, _D3DDDI_EXECUTIONSTATEESCAPE, d3dumddi/D3DDDI_EXECUTIONSTATEESCAPE, display.d3dddi_executionstateescape"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dumddi.h
apiname:
-	D3DDDI_EXECUTIONSTATEESCAPE
product: Windows
targetos: Windows
req.typenames: D3DDDI_EXECUTIONSTATEESCAPE
---

# _D3DDDI_EXECUTIONSTATEESCAPE structure


## -description


Specifies the state of the device.


## -syntax


````
typedef struct _D3DDDI_EXECUTIONSTATEESCAPE {
  D3DDDI_DEVICEEXECUTION_STATE State;
} D3DDDI_EXECUTIONSTATEESCAPE;
````


## -struct-fields




### -field State

[Out] A value of type <a href="..\d3dumddi\ne-d3dumddi-_d3dddi_deviceexecution_state.md">D3DDDI_DEVICEEXECUTION_STATE</a> that indicates the state of the device.


## -see-also

<a href="..\d3dumddi\ne-d3dumddi-_d3dddi_deviceexecution_state.md">D3DDDI_DEVICEEXECUTION_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_EXECUTIONSTATEESCAPE structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

