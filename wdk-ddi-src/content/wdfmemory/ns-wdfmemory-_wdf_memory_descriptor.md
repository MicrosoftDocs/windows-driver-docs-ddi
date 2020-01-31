---
UID: NS:wdfmemory._WDF_MEMORY_DESCRIPTOR
title: _WDF_MEMORY_DESCRIPTOR (wdfmemory.h)
description: The WDF_MEMORY_DESCRIPTOR structure describes a memory buffer.
old-location: wdf\wdf_memory_descriptor.htm
tech.root: wdf
ms.assetid: 0683cb81-4ae7-4296-b46a-ad2e8b25a781
ms.date: 02/26/2018
ms.keywords: "*PWDF_MEMORY_DESCRIPTOR, DFMemoryObjectRef_2c2271fb-6f3f-466d-b1dd-d254bc7ec96e.xml, PWDF_MEMORY_DESCRIPTOR, PWDF_MEMORY_DESCRIPTOR structure pointer, WDF_MEMORY_DESCRIPTOR, WDF_MEMORY_DESCRIPTOR structure, _WDF_MEMORY_DESCRIPTOR, kmdf.wdf_memory_descriptor, wdf.wdf_memory_descriptor, wdfmemory/PWDF_MEMORY_DESCRIPTOR, wdfmemory/WDF_MEMORY_DESCRIPTOR"
f1_keywords:
 - "wdfmemory/WDF_MEMORY_DESCRIPTOR"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfmemory.h
api_name:
- WDF_MEMORY_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: WDF_MEMORY_DESCRIPTOR, *PWDF_MEMORY_DESCRIPTOR
---

# _WDF_MEMORY_DESCRIPTOR structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_MEMORY_DESCRIPTOR</b> structure describes a memory buffer.


## -struct-fields




### -field Type

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ne-wdfmemory-_wdf_memory_descriptor_type">WDF_MEMORY_DESCRIPTOR_TYPE</a>-typed value that identifies the type of buffer description that this <b>WDF_MEMORY_DESCRIPTOR</b> structure contains.


### -field u

A union of three structures, one of which describes a buffer.


### -field u.BufferType

If the <b>Type</b> member is <b>WdfMemoryDescriptorTypeBuffer</b>, the members of the <b>BufferType</b> structure describe a buffer. This structure contains the following two members:


### -field u.BufferType.Buffer

A pointer to a buffer. 


### -field u.BufferType.Length

The length, in bytes, of the buffer. 


### -field u.MdlType

If the <b>Type</b> member is <b>WdfMemoryDescriptorTypeMdl</b>, the members of the <b>MdlType</b> structure describe a buffer. This structure contains the following two members:


### -field u.MdlType.Mdl

A pointer to a memory descriptor list (MDL). 


### -field u.MdlType.BufferLength

The length, in bytes, of the buffer.


### -field u.HandleType

If the <b>Type</b> member is <b>WdfMemoryDescriptorTypeHandle</b>, the members of the <b>HandleType</b> structure describe a buffer. This structure contains the following two members:


### -field u.HandleType.Memory

A handle to a framework memory object. 


### -field u.HandleType.Offsets

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that describes a subsection of the buffer that is represented by the memory object. 


## -remarks



The <b>WDF_MEMORY_DESCRIPTOR</b> structure is used as input to several of the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/">I/O target object methods</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/">USB device object methods</a>.

To initialize a <b>WDF_MEMORY_DESCRIPTOR</b> structure, your driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdf_memory_descriptor_init_buffer">WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdf_memory_descriptor_init_mdl">WDF_MEMORY_DESCRIPTOR_INIT_MDL</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdf_memory_descriptor_init_handle">WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdfmemory_offset">WDFMEMORY_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ne-wdfmemory-_wdf_memory_descriptor_type">WDF_MEMORY_DESCRIPTOR_TYPE</a>
 

 

