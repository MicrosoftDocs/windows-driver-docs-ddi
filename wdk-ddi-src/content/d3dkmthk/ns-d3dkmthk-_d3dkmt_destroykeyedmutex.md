---
UID: NS:d3dkmthk._D3DKMT_DESTROYKEYEDMUTEX
title: "_D3DKMT_DESTROYKEYEDMUTEX"
author: windows-driver-content
description: The D3DKMT_DESTROYKEYEDMUTEX structure describes a keyed mutex that the D3DKMTDestroyKeyedMutex function destroys.
old-location: display\d3dkmt_destroykeyedmutex.htm
old-project: display
ms.assetid: b7903bf8-ef62-4224-a81d-4b41f36e2061
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DKMT_DESTROYKEYEDMUTEX, d3dkmthk/D3DKMT_DESTROYKEYEDMUTEX, display.d3dkmt_destroykeyedmutex, OpenGL_Structs_4eb8a9cb-d2b1-445b-b545-5ec0a017a61c.xml, D3DKMT_DESTROYKEYEDMUTEX, D3DKMT_DESTROYKEYEDMUTEX structure [Display Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_DESTROYKEYEDMUTEX is supported beginning with the Windows 7 operating system.
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
-	D3DKMT_DESTROYKEYEDMUTEX
product: Windows
targetos: Windows
req.typenames: D3DKMT_DESTROYKEYEDMUTEX
---

# _D3DKMT_DESTROYKEYEDMUTEX structure


## -description


The D3DKMT_DESTROYKEYEDMUTEX structure describes a keyed mutex that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroykeyedmutex.md">D3DKMTDestroyKeyedMutex</a> function destroys. 


## -syntax


````
typedef struct _D3DKMT_DESTROYKEYEDMUTEX {
  D3DKMT_HANDLE hKeyedMutex;
} D3DKMT_DESTROYKEYEDMUTEX;
````


## -struct-fields




### -field hKeyedMutex

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object to destroy. 


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroykeyedmutex.md">D3DKMTDestroyKeyedMutex</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DESTROYKEYEDMUTEX structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

