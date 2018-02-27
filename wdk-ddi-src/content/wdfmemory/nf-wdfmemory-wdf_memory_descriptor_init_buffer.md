---
UID: NF:wdfmemory.WDF_MEMORY_DESCRIPTOR_INIT_BUFFER
title: WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function
author: windows-driver-content
description: The WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function initializes a WDF_MEMORY_DESCRIPTOR structure so that it describes a specified buffer.
old-location: wdf\wdf_memory_descriptor_init_buffer.htm
old-project: wdf
ms.assetid: 16e1b0cb-8543-4700-8f8c-d7301c6de622
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFMemoryObjectRef_706a9ee6-c0f1-4cb4-a887-cbb535d94d17.xml, WDF_MEMORY_DESCRIPTOR_INIT_BUFFER, WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function, kmdf.wdf_memory_descriptor_init_buffer, wdf.wdf_memory_descriptor_init_buffer, wdfmemory/WDF_MEMORY_DESCRIPTOR_INIT_BUFFER
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
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
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
-	WDF_MEMORY_DESCRIPTOR_INIT_BUFFER
product: Windows
targetos: Windows
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
req.product: Windows 10 or later.
---

# WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</b> function initializes a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure so that it describes a specified buffer.


## -syntax


````
VOID WDF_MEMORY_DESCRIPTOR_INIT_BUFFER(
  _Out_ PWDF_MEMORY_DESCRIPTOR Descriptor,
  _In_  PVOID                  Buffer,
  _In_  ULONG                  BufferLength
);
````


## -parameters




### -param Descriptor [out]

A pointer to a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure.


### -param Buffer [in]

A pointer to a memory buffer.


### -param BufferLength [in]

The size, in bytes, of the memory buffer that <i>Buffer</i> points to.


## -returns



None




## -remarks



The <b>WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</b> function zeros the specified <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure and sets the structure's <b>Type</b> member to <b>WdfMemoryDescriptorTypeBuffer</b>. Then it sets the structure's <b>u.BufferType.Buffer</b> and <b>u.BufferType.Length</b> members to the values that the <i>Buffer</i> and <i>BufferLength</i> parameters specify, respectively.


#### Examples

For a code example that uses <b>WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</b>, see <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_mdl.md">WDF_MEMORY_DESCRIPTOR_INIT_MDL</a>



<a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_handle.md">WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</a>



<a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

