---
UID: NF:wdfmemory.WDF_MEMORY_DESCRIPTOR_INIT_MDL
title: WDF_MEMORY_DESCRIPTOR_INIT_MDL function (wdfmemory.h)
description: The WDF_MEMORY_DESCRIPTOR_INIT_MDL function initializes a WDF_MEMORY_DESCRIPTOR structure so that it describes a specified memory descriptor list (MDL).
old-location: wdf\wdf_memory_descriptor_init_mdl.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_MEMORY_DESCRIPTOR_INIT_MDL function"]
ms.keywords: DFMemoryObjectRef_f5eb00be-fd17-49bf-87dd-4fde1b06d65e.xml, WDF_MEMORY_DESCRIPTOR_INIT_MDL, WDF_MEMORY_DESCRIPTOR_INIT_MDL function, kmdf.wdf_memory_descriptor_init_mdl, wdf.wdf_memory_descriptor_init_mdl, wdfmemory/WDF_MEMORY_DESCRIPTOR_INIT_MDL
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_MEMORY_DESCRIPTOR_INIT_MDL
 - wdfmemory/WDF_MEMORY_DESCRIPTOR_INIT_MDL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfmemory.h
api_name:
 - WDF_MEMORY_DESCRIPTOR_INIT_MDL
---

# WDF_MEMORY_DESCRIPTOR_INIT_MDL function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_MEMORY_DESCRIPTOR_INIT_MDL</b> function initializes a <a href="/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure so that it describes a specified memory descriptor list (MDL).

## -parameters

### -param Descriptor 

[out]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure.

### -param Mdl 

[in]
A pointer to an MDL that describes a buffer.

### -param BufferLength 

[in]
The size, in bytes, of the buffer that <i>Mdl</i> specifies.

## -remarks

The <b>WDF_MEMORY_DESCRIPTOR_INIT_MDL</b> function zeros the specified <a href="/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure and sets the structure's <b>Type</b> member to <b>WdfMemoryDescriptorTypeMdl</b>. Then it sets the structure's <b>u.MdlType.Mdl</b> and <b>u.MdlType.BufferLength</b> members to the values that the <i>Mdl</i> and <i>BufferLength</i> parameters specify, respectively.


#### Examples

The following code example allocates a buffer, creates an MDL for the buffer, and uses the MDL to initialize a <a href="/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure.

```cpp
PVOID  pBuffer = NULL;
PMDL  pMdl = NULL;

pBuffer = ExAllocatePoolWithTag(
                                NonPagedPool, 
                                BUFFER_LENGTH, 
                                IOTARGET_DRIVER_TAG
                                );
if (pBuffer == NULL){
    Status = STATUS_UNSUCCESSFUL;
    goto Cleanup;
}
pMdl = IoAllocateMdl(
                     pBuffer,
                     BUFFER_LENGTH,
                     FALSE,
                     TRUE,
                     NULL
                     );
if (pMdl == NULL){
    Status = STATUS_UNSUCCESSFUL;
    goto Cleanup;
}
MmBuildMdlForNonPagedPool(pMdl);
WDF_MEMORY_DESCRIPTOR_INIT_MDL(
                               pInputBuffer,
                               pMdl,
                               BUFFER_LENGTH
                               );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmbuildmdlfornonpagedpool">MmBuildMdlForNonPagedPool</a>



<a href="/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdf_memory_descriptor_init_buffer">WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdf_memory_descriptor_init_handle">WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</a>
