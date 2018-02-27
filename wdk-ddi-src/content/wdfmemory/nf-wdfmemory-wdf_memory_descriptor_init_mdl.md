---
UID: NF:wdfmemory.WDF_MEMORY_DESCRIPTOR_INIT_MDL
title: WDF_MEMORY_DESCRIPTOR_INIT_MDL function
author: windows-driver-content
description: The WDF_MEMORY_DESCRIPTOR_INIT_MDL function initializes a WDF_MEMORY_DESCRIPTOR structure so that it describes a specified memory descriptor list (MDL).
old-location: wdf\wdf_memory_descriptor_init_mdl.htm
old-project: wdf
ms.assetid: 2f46b268-2d8c-455a-81e3-a79f48e704c7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFMemoryObjectRef_f5eb00be-fd17-49bf-87dd-4fde1b06d65e.xml, WDF_MEMORY_DESCRIPTOR_INIT_MDL, WDF_MEMORY_DESCRIPTOR_INIT_MDL function, kmdf.wdf_memory_descriptor_init_mdl, wdf.wdf_memory_descriptor_init_mdl, wdfmemory/WDF_MEMORY_DESCRIPTOR_INIT_MDL
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
req.ddi-compliance: MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfmemory.h
api_name:
-	WDF_MEMORY_DESCRIPTOR_INIT_MDL
product: Windows
targetos: Windows
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
req.product: Windows 10 or later.
---

# WDF_MEMORY_DESCRIPTOR_INIT_MDL function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_MEMORY_DESCRIPTOR_INIT_MDL</b> function initializes a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure so that it describes a specified memory descriptor list (MDL).


## -syntax


````
VOID WDF_MEMORY_DESCRIPTOR_INIT_MDL(
  _Out_ PWDF_MEMORY_DESCRIPTOR Descriptor,
  _In_  PMDL                   Mdl,
  _In_  ULONG                  BufferLength
);
````


## -parameters




### -param Descriptor [out]

A pointer to a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure.


### -param Mdl [in]

A pointer to an MDL that describes a buffer.


### -param BufferLength [in]

The size, in bytes, of the buffer that <i>Mdl</i> specifies.


## -returns



None




## -remarks



The <b>WDF_MEMORY_DESCRIPTOR_INIT_MDL</b> function zeros the specified <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure and sets the structure's <b>Type</b> member to <b>WdfMemoryDescriptorTypeMdl</b>. Then it sets the structure's <b>u.MdlType.Mdl</b> and <b>u.MdlType.BufferLength</b> members to the values that the <i>Mdl</i> and <i>BufferLength</i> parameters specify, respectively.


#### Examples

The following code example allocates a buffer, creates an MDL for the buffer, and uses the MDL to initialize a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PVOID  pBuffer = NULL;
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
                               );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a>



<a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_buffer.md">WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</a>



<a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_handle.md">WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</a>



<a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



<a href="..\wdm\nf-wdm-mmbuildmdlfornonpagedpool.md">MmBuildMdlForNonPagedPool</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_MEMORY_DESCRIPTOR_INIT_MDL function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

