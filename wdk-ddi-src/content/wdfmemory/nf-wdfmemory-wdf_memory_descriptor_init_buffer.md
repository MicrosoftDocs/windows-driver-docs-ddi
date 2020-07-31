---
UID: NF:wdfmemory.WDF_MEMORY_DESCRIPTOR_INIT_BUFFER
title: WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function (wdfmemory.h)
description: The WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function initializes a WDF_MEMORY_DESCRIPTOR structure so that it describes a specified buffer.
old-location: wdf\wdf_memory_descriptor_init_buffer.htm
tech.root: wdf
ms.assetid: 16e1b0cb-8543-4700-8f8c-d7301c6de622
ms.date: 02/26/2018
keywords: ["WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function"]
ms.keywords: DFMemoryObjectRef_706a9ee6-c0f1-4cb4-a887-cbb535d94d17.xml, WDF_MEMORY_DESCRIPTOR_INIT_BUFFER, WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function, kmdf.wdf_memory_descriptor_init_buffer, wdf.wdf_memory_descriptor_init_buffer, wdfmemory/WDF_MEMORY_DESCRIPTOR_INIT_BUFFER
f1_keywords:
 - "wdfmemory/WDF_MEMORY_DESCRIPTOR_INIT_BUFFER"
 - "WDF_MEMORY_DESCRIPTOR_INIT_BUFFER"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfmemory.h
api_name:
- WDF_MEMORY_DESCRIPTOR_INIT_BUFFER
targetos: Windows
req.typenames: 
---

# WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure so that it describes a specified buffer.


## -parameters




### -param Descriptor [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure.


### -param Buffer [in]

A pointer to a memory buffer.


### -param BufferLength [in]

The size, in bytes, of the memory buffer that <i>Buffer</i> points to.


## -remarks



The <b>WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure and sets the structure's <b>Type</b> member to <b>WdfMemoryDescriptorTypeBuffer</b>. Then it sets the structure's <b>u.BufferType.Buffer</b> and <b>u.BufferType.Length</b> members to the values that the <i>Buffer</i> and <i>BufferLength</i> parameters specify, respectively.


#### Examples

For a code example that uses <b>WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdf_memory_descriptor_init_handle">WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdf_memory_descriptor_init_mdl">WDF_MEMORY_DESCRIPTOR_INIT_MDL</a>
 

 

