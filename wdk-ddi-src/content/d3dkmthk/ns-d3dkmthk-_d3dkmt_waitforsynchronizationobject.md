---
UID: NS:d3dkmthk._D3DKMT_WAITFORSYNCHRONIZATIONOBJECT
title: "_D3DKMT_WAITFORSYNCHRONIZATIONOBJECT"
author: windows-driver-content
description: The D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure contains information about the synchronization events that the D3DKMTWaitForSynchronizationObject function waits for to occur.
old-location: display\d3dkmt_waitforsynchronizationobject.htm
old-project: display
ms.assetid: 47d0330e-5413-4729-b103-c1a4d6c648e1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DKMT_WAITFORSYNCHRONIZATIONOBJECT, D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure [Display Devices], OpenGL_Structs_5498c651-0ef6-4114-9821-de193980f879.xml, D3DKMT_WAITFORSYNCHRONIZATIONOBJECT, display.d3dkmt_waitforsynchronizationobject, d3dkmthk/D3DKMT_WAITFORSYNCHRONIZATIONOBJECT"
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
-	D3DKMT_WAITFORSYNCHRONIZATIONOBJECT
product: Windows
targetos: Windows
req.typenames: D3DKMT_WAITFORSYNCHRONIZATIONOBJECT
---

# _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure


## -description


The D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure contains information about the synchronization events that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforsynchronizationobject.md">D3DKMTWaitForSynchronizationObject</a> function waits for to occur. 


## -syntax


````
typedef struct _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT {
  D3DKMT_HANDLE hContext;
  UINT          ObjectCount;
  D3DKMT_HANDLE ObjectHandleArray[D3DDDI_MAX_OBJECT_WAITED_ON];
} D3DKMT_WAITFORSYNCHRONIZATIONOBJECT;
````


## -struct-fields




#### - hContext

[in] A kernel-mode handle to the context stream in which a wait for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted.


#### - ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array. 


#### - ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for. The D3DDDI_MAX_OBJECT_WAITED_ON constant, which is defined as 32, indicates the maximum number of synchronization events that the context can wait for.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforsynchronizationobject.md">D3DKMTWaitForSynchronizationObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_WAITFORSYNCHRONIZATIONOBJECT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

