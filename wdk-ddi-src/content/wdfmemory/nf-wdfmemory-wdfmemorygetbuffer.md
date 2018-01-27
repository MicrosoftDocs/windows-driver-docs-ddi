---
UID: NF:wdfmemory.WdfMemoryGetBuffer
title: WdfMemoryGetBuffer function
author: windows-driver-content
description: The WdfMemoryGetBuffer method returns a pointer to the buffer that is associated with a specified memory object.
old-location: wdf\wdfmemorygetbuffer.htm
old-project: wdf
ms.assetid: a5044eb5-d619-4adb-a00c-2d01e0311ade
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfMemoryGetBuffer method, kmdf.wdfmemorygetbuffer, wdfmemory/WdfMemoryGetBuffer, WdfMemoryGetBuffer, PFN_WDFMEMORYGETBUFFER, wdf.wdfmemorygetbuffer, DFMemoryObjectRef_6f8615ee-5e34-46c5-8c83-4b52433753aa.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctlA, MemAfterReqCompletedReadA, MemAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname: 
-	WdfMemoryGetBuffer
product: Windows
targetos: Windows
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
req.product: Windows 10 or later.
---

# WdfMemoryGetBuffer function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfMemoryGetBuffer</b> method returns a pointer to the buffer that is associated with a specified memory object.


## -syntax


````
PVOID WdfMemoryGetBuffer(
  _In_      WDFMEMORY Memory,
  _Out_opt_ size_t    *BufferSize
);
````


## -parameters




### -param Memory [in]

A handle to a framework memory object.


### -param BufferSize [out, optional]

A pointer to a location that receives the size, in bytes, of the memory buffer. This parameter is optional and can be <b>NULL</b>.


## -returns


<b>WdfMemoryGetBuffer</b> returns a pointer to the memory buffer.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


For more information about framework memory objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.

<b>WdfMemoryGetBuffer</b> can be called at any IRQL.



## -see-also

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a>

<a href="..\wdfobject\nf-wdfobject-wdfobjectcontextgetobject.md">WdfObjectContextGetObject</a>

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfMemoryGetBuffer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

