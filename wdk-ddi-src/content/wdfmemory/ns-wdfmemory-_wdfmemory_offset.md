---
UID: NS:wdfmemory._WDFMEMORY_OFFSET
title: "_WDFMEMORY_OFFSET"
author: windows-driver-content
description: The WDFMEMORY_OFFSET structure identifies a subsection of a memory object's buffer.
old-location: wdf\wdfmemory_offset.htm
old-project: wdf
ms.assetid: ca891a21-e7ab-4230-bfc4-adfdb413838b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDFMEMORY_OFFSET, PWDFMEMORY_OFFSET structure pointer, kmdf.wdfmemory_offset, wdfmemory/PWDFMEMORY_OFFSET, PWDFMEMORY_OFFSET, DFMemoryObjectRef_d6ea5bd1-f672-4624-9663-f1e5f70eb8b2.xml, WDFMEMORY_OFFSET structure, _WDFMEMORY_OFFSET, wdfmemory/WDFMEMORY_OFFSET, *PWDFMEMORY_OFFSET, wdf.wdfmemory_offset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfmemory.h
apiname:
-	WDFMEMORY_OFFSET
product: Windows
targetos: Windows
req.typenames: "*PWDFMEMORY_OFFSET, WDFMEMORY_OFFSET"
req.product: Windows 10 or later.
---

# _WDFMEMORY_OFFSET structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDFMEMORY_OFFSET</b> structure identifies a subsection of a memory object's buffer.


## -syntax


````
typedef struct _WDFMEMORY_OFFSET {
  size_t BufferOffset;
  size_t BufferLength;
} WDFMEMORY_OFFSET, *PWDFMEMORY_OFFSET;
````


## -struct-fields




#### - BufferOffset

A byte offset from the beginning of the memory object's buffer. This offset identifies the location of the buffer's subsection. A value of zero represents the beginning of the buffer.


#### - BufferLength

The length, in bytes, of the buffer's subsection. A value of zero represents the entire buffer.


## -remarks


The <b>WDFMEMORY_OFFSET</b> structure is used as a member of the <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure and as an input parameter to various I/O target object methods.



## -see-also

<a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDFMEMORY_OFFSET structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

