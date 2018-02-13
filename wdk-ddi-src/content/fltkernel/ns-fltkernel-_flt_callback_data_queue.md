---
UID: NS:fltkernel._FLT_CALLBACK_DATA_QUEUE
title: "_FLT_CALLBACK_DATA_QUEUE"
author: windows-driver-content
description: FLT_CALLBACK_DATA_QUEUE is an opaque structure that is used to specify the callback routines for a minifilter's callback data queue. Do not set the members of this structure directly. Use FltCbdqInitialize to initialize this structure.
old-location: ifsk\flt_callback_data_queue.htm
old-project: ifsk
ms.assetid: bd0defc1-7c06-4b54-b4e3-3c17c49a6c57
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: PFLT_CALLBACK_DATA_QUEUE structure pointer [Installable File System Drivers], FLT_CALLBACK_DATA_QUEUE structure [Installable File System Drivers], *PFLT_CALLBACK_DATA_QUEUE, _FLT_CALLBACK_DATA_QUEUE, FLT_CALLBACK_DATA_QUEUE, PFLT_CALLBACK_DATA_QUEUE, fltkernel/PFLT_CALLBACK_DATA_QUEUE, ifsk.flt_callback_data_queue, FltSystemStructures_d43817d6-bc53-407d-8a3f-c6268112eb6e.xml, fltkernel/FLT_CALLBACK_DATA_QUEUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: FltKernel.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fltkernel.h
apiname:
-	FLT_CALLBACK_DATA_QUEUE
product: Windows
targetos: Windows
req.typenames: "*PFLT_CALLBACK_DATA_QUEUE, FLT_CALLBACK_DATA_QUEUE"
---

# _FLT_CALLBACK_DATA_QUEUE structure


## -description


FLT_CALLBACK_DATA_QUEUE is an opaque structure that is used to specify the callback routines for a minifilter's callback data queue. Do not set the members of this structure directly. Use <a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a> to initialize this structure. 




## -struct-fields


## -see-also

<a href="..\fltkernel\nf-fltkernel-fltcbdqinsertio.md">FltCbdqInsertIo</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqenable.md">FltCbdqEnable</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqremovenextio.md">FltCbdqRemoveNextIo</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqremoveio.md">FltCbdqRemoveIo</a>



<a href="..\fltkernel\nf-fltkernel-fltcbdqdisable.md">FltCbdqDisable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_CALLBACK_DATA_QUEUE structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

