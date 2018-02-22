---
UID: NS:d3dkmthk._D3DKMT_DESTROYCONTEXT
title: "_D3DKMT_DESTROYCONTEXT"
author: windows-driver-content
description: The D3DKMT_DESTROYCONTEXT structure contains a handle to a kernel-mode device context to release.
old-location: display\d3dkmt_destroycontext.htm
old-project: display
ms.assetid: 116c0fa7-ac3c-4a56-804c-637514a19c73
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: OpenGL_Structs_97f52665-09e6-4f11-b2cc-a7abcc61827c.xml, D3DKMT_DESTROYCONTEXT, D3DKMT_DESTROYCONTEXT structure [Display Devices], _D3DKMT_DESTROYCONTEXT, d3dkmthk/D3DKMT_DESTROYCONTEXT, display.d3dkmt_destroycontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
apiname:
-	D3DKMT_DESTROYCONTEXT
product: Windows
targetos: Windows
req.typenames: D3DKMT_DESTROYCONTEXT
---

# _D3DKMT_DESTROYCONTEXT structure


## -description


The D3DKMT_DESTROYCONTEXT structure contains a handle to a kernel-mode device context to release.


## -syntax


````
typedef struct _D3DKMT_DESTROYCONTEXT {
  D3DKMT_HANDLE hContext;
} D3DKMT_DESTROYCONTEXT;
````


## -struct-fields




### -field hContext

[in] A handle to the device context that the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) supplied and that is returned from the call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatecontext.md">D3DKMTCreateContext</a> function.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroycontext.md">D3DKMTDestroyContext</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatecontext.md">D3DKMTCreateContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DESTROYCONTEXT structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

