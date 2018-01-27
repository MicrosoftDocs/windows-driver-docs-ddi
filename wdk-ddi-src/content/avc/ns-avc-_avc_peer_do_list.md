---
UID: NS:avc._AVC_PEER_DO_LIST
title: _AVC_PEER_DO_LIST
author: windows-driver-content
description: The AVC_PEER_DO_LIST describes all nonvirtual (peer) instances of avc.sys.
old-location: stream\avc_peer_do_list.htm
old-project: stream
ms.assetid: 5420df9b-35e7-49b4-97dc-a1d61623551c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: AVC_PEER_DO_LIST, *PAVC_PEER_DO_LIST, AVC_PEER_DO_LIST structure [Streaming Media Devices], PAVC_PEER_DO_LIST structure pointer [Streaming Media Devices], avc/PAVC_PEER_DO_LIST, _AVC_PEER_DO_LIST, avcref_69feff07-d80c-4d5a-a5d8-fe942dfc5e26.xml, PAVC_PEER_DO_LIST, avc/AVC_PEER_DO_LIST, stream.avc_peer_do_list
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
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
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	avc.h
apiname: 
-	AVC_PEER_DO_LIST
product: Windows
targetos: Windows
req.typenames: AVC_PEER_DO_LIST, *PAVC_PEER_DO_LIST
---

# _AVC_PEER_DO_LIST structure


## -description


The AVC_PEER_DO_LIST describes all nonvirtual (peer) instances of <i>avc.sys</i>.


## -syntax


````
typedef struct _AVC_PEER_DO_LIST {
  ULONG          Count;
  PDEVICE_OBJECT *Objects;
} AVC_PEER_DO_LIST, *PAVC_PEER_DO_LIST;
````


## -struct-fields




### -field Count

Ignored on input. On output, set to the number of objects in the list. If zero, the caller must not attempt to dereference the <b>Objects</b> member (it is set to <b>NULL</b>).


### -field Objects

Ignored on input. On output (and if the <b>Count</b> member is not zero) <b>Objects</b> contains a pointer to a contiguous array of DEVICE_OBJECT pointers. The caller must release the reference held on each object (by using <b>ObDereferenceObject</b>), and free the memory containing the list (by using <b>ExFreePool</b>) when finished with it.


## -remarks


This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554168">AVC_FUNCTION_PEER_DO_LIST</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.



## -see-also

<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554168">AVC_FUNCTION_PEER_DO_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_PEER_DO_LIST structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

