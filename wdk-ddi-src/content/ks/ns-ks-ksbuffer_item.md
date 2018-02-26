---
UID: NS:ks.KSBUFFER_ITEM
title: KSBUFFER_ITEM
author: windows-driver-content
description: The KSBUFFER_ITEM structure is used to store a list of data buffers copied from the event source, which can be retrieved by the event sink through KSEVENT_TYPE_QUERYBUFFER.
old-location: stream\ksbuffer_item.htm
old-project: stream
ms.assetid: e4b11ff8-cafc-456c-b274-e47b85ac77d0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSBUFFER_ITEM, ,, B, E, F, I, K, KSBUFFER_ITEM, KSBUFFER_ITEM structure [Streaming Media Devices], M, P, PKSBUFFER_ITEM, PKSBUFFER_ITEM structure pointer [Streaming Media Devices], R, S, T, U, _, ks-struct_6c2444cb-9f6c-4ab7-ab79-ae969705db59.xml, ks/KSBUFFER_ITEM, ks/PKSBUFFER_ITEM, stream.ksbuffer_item"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KSBUFFER_ITEM
product: Windows
targetos: Windows
req.typenames: KSBUFFER_ITEM, *PKSBUFFER_ITEM
---

# KSBUFFER_ITEM structure


## -description


The KSBUFFER_ITEM structure is used to store a list of data buffers copied from the event source, which can be retrieved by the event sink through KSEVENT_TYPE_QUERYBUFFER.


## -syntax


````
typedef struct {
  KSDPC_ITEM DpcItem;
  LIST_ENTRY BufferList;
} KSBUFFER_ITEM, *PKSBUFFER_ITEM;
````


## -struct-fields




### -field DpcItem

A structure of type <a href="..\ks\ns-ks-ksdpc_item.md">KSDPC_ITEM</a>. May be used by internal DPCs; do not use for data buffering.


### -field BufferList

Specifies the head of a list of pool allocated buffers that are created by calls to <a href="..\ks\nf-ks-ksgeneratedataevent.md">KsGenerateDataEvent</a> for events that have buffering enabled.


## -remarks



KSBUFFER_ITEM extends the normal deferred procedure call (DPC) structure, which may be needed for event generation, but does not use the structure itself.




## -see-also

<a href="..\ks\nf-ks-ksgeneratedataevent.md">KsGenerateDataEvent</a>



<a href="..\ks\ns-ks-ksdpc_item.md">KSDPC_ITEM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSBUFFER_ITEM structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

