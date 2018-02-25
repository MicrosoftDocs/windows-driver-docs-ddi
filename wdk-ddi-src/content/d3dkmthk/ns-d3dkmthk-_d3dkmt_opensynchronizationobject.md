---
UID: NS:d3dkmthk._D3DKMT_OPENSYNCHRONIZATIONOBJECT
title: "_D3DKMT_OPENSYNCHRONIZATIONOBJECT"
author: windows-driver-content
description: The D3DKMT_OPENSYNCHRONIZATIONOBJECT structure describes a synchronization object that the D3DKMTOpenSynchronizationObject function opens.
old-location: display\d3dkmt_opensynchronizationobject.htm
old-project: display
ms.assetid: 58e71ce5-29d0-4ee2-8d91-02230021110d
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, A, B, C, D, D3DKMT_OPENSYNCHRONIZATIONOBJECT, D3DKMT_OPENSYNCHRONIZATIONOBJECT structure [Display Devices], E, H, I, J, K, M, N, O, OpenGL_Structs_61f9f676-2b21-4cb3-8c6a-9f25ce3ac2bc.xml, P, R, S, T, Y, Z, _, _D3DKMT_OPENSYNCHRONIZATIONOBJECT, d3dkmthk/D3DKMT_OPENSYNCHRONIZATIONOBJECT, display.d3dkmt_opensynchronizationobject"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_OPENSYNCHRONIZATIONOBJECT is supported beginning with the Windows 7 operating system.
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
-	D3DKMT_OPENSYNCHRONIZATIONOBJECT
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENSYNCHRONIZATIONOBJECT
---

# _D3DKMT_OPENSYNCHRONIZATIONOBJECT structure


## -description


The D3DKMT_OPENSYNCHRONIZATIONOBJECT structure describes a synchronization object that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopensynchronizationobject.md">D3DKMTOpenSynchronizationObject</a> function opens. 


## -syntax


````
typedef struct _D3DKMT_OPENSYNCHRONIZATIONOBJECT {
  D3DKMT_HANDLE hSharedHandle;
  D3DKMT_HANDLE hSyncObject;
  UINT64        Reserved[8];
} D3DKMT_OPENSYNCHRONIZATIONOBJECT;
````


## -struct-fields




### -field hSharedHandle

[in] A shared handle to the synchronization object to be opened. 


### -field hSyncObject

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode synchronization object in the current process. 


### -field Reserved

[in] An array of 64-bit values that are reserved for future use. 


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopensynchronizationobject.md">D3DKMTOpenSynchronizationObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OPENSYNCHRONIZATIONOBJECT structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

