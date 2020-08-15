---
UID: NF:ntifs.FsRtlAllocateExtraCreateParameterList
title: FsRtlAllocateExtraCreateParameterList function (ntifs.h)
description: The FsRtlAllocateExtraCreateParameterList routine allocates paged pool memory for an ECP_LIST structure and generates a pointer to that structure.
old-location: ifsk\fsrtlallocateextracreateparameterlist.htm
tech.root: ifsk
ms.assetid: 93888920-73b2-41e4-8d49-e5235ee93307
ms.date: 04/16/2018
keywords: ["FsRtlAllocateExtraCreateParameterList function"]
ms.keywords: FsRtlAllocateExtraCreateParameterList, FsRtlAllocateExtraCreateParameterList routine [Installable File System Drivers], fsrtlref_2d552d23-4312-4203-91fb-c6cf6fb39681.xml, ifsk.fsrtlallocateextracreateparameterlist, ntifs/FsRtlAllocateExtraCreateParameterList
f1_keywords:
 - "ntifs/FsRtlAllocateExtraCreateParameterList"
 - "FsRtlAllocateExtraCreateParameterList"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlAllocateExtraCreateParameterList routine is available starting with Windows Vista.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlAllocateExtraCreateParameterList
targetos: Windows
req.typenames: 
---

# FsRtlAllocateExtraCreateParameterList function


## -description


The <b>FsRtlAllocateExtraCreateParameterList</b> routine allocates paged pool memory for an <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a> structure and generates a pointer to that structure.


## -parameters




### -param Flags 
[in]
Defines pool allocation options.  If the FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA flag is combined with the <i>Flags</i> parameter by using a bitwise OR operation, any pool allocated by <b>FsRtlAllocateExtraCreateParameterList</b>  will be charged against the current process' memory quota.


### -param EcpList 
[out]
Receives a pointer to an initialized ECP list structure.  If <b>FsRtlAllocateExtraCreateParameterList</b>  failed to allocate sufficient pool, <i>*EcpList</i> will be <b>NULL</b> and <b>FsRtlAllocateExtraCreateParameterList</b>  will return status code STATUS_INSUFFICIENT_RESOURCES.


## -returns



<b>FsRtlAllocateExtraCreateParameterList</b> can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FsRtlAllocateExtraCreateParameterList</b> was unable to allocate sufficient memory for an ECP list structure.  In this case, <i>*EcpList</i> will be <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The memory for the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a> structure was successfully allocated and initialized.  In this case, a pointer to the initialized list structure is returned in the <i>EcpList</i> parameter.

</td>
</tr>
</table>
 




## -remarks



Whether the operating system automatically frees memory that <b>FsRtlAllocateExtraCreateParameterList</b> allocates depends on when <b>FsRtlAllocateExtraCreateParameterList</b> is called, as shown in the following situations:

<ul>
<li>
A caller can invoke <b>FsRtlAllocateExtraCreateParameterList</b> to allocate the ECP_LIST and add one or more ECP context structures before the caller invokes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a> routine. In this situation, the operating system does not free any of the ECP context structures. Therefore, the caller can make multiple calls to <b>IoCreateFileEx</b> with the same ECP set. When the caller is done with the ECP_LIST, the caller must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546005">FsRtlFreeExtraCreateParameterList</a> routine to free the ECP_LIST.

</li>
<li>
While a file system or file system filter driver processes an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> request, the file system or file system filter driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546179">FsRtlInsertExtraCreateParameter</a> to attach an ECP to an existing ECP_LIST. If the ECP_LIST does not exist, the caller must call <b>FsRtlAllocateExtraCreateParameterList</b> to create the ECP_LIST. In this situation, the ECP_LIST and the ECP context structure are automatically cleaned up by the I/O manager when the create operation completes. This allows a file system's or filter driver's ECP to be properly propagated across the processing of reparse points. This process might require multiple IRP_MJ_CREATE requests to be generated. 

</li>
</ul>
If the FSRTL_ALLOCATE_ECPLIST_FLAG_CHARGE_QUOTA flag is used with the <i>Flags</i> parameter, a pageable pool is allocated. Otherwise, a pageable pool is allocated by using an internal lookaside list.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameter">FltAllocateExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter">FltFreeExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameterlist">FltFreeExtraCreateParameterList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>
 

 

