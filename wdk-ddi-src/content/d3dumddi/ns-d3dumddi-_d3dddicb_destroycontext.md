---
UID: NS:d3dumddi._D3DDDICB_DESTROYCONTEXT
title: "_D3DDDICB_DESTROYCONTEXT"
author: windows-driver-content
description: The D3DDDICB_DESTROYCONTEXT structure contains the handle to a context to destroy.
old-location: display\d3dddicb_destroycontext.htm
old-project: display
ms.assetid: 31f1577d-72ba-495a-97e4-0569bdbc0ed7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DDDICB_DESTROYCONTEXT, D3DDDICB_DESTROYCONTEXT structure [Display Devices], D3DDDICB_DESTROYCONTEXT, d3dumddi/D3DDDICB_DESTROYCONTEXT, display.d3dddicb_destroycontext, D3D_param_Structs_40e3c0f9-b30b-4fab-8b4a-a1809f03d0ba.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDICB_DESTROYCONTEXT
product: Windows
targetos: Windows
req.typenames: D3DDDICB_DESTROYCONTEXT
---

# _D3DDDICB_DESTROYCONTEXT structure


## -description


The D3DDDICB_DESTROYCONTEXT structure contains the handle to a context to destroy.


## -syntax


````
typedef struct _D3DDDICB_DESTROYCONTEXT {
  HANDLE hContext;
} D3DDDICB_DESTROYCONTEXT;
````


## -struct-fields




### -field hContext

[in] A handle that the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function returns and that identifies the context to destroy. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycontextcb.md">pfnDestroyContextCb</a>

<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_DESTROYCONTEXT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

