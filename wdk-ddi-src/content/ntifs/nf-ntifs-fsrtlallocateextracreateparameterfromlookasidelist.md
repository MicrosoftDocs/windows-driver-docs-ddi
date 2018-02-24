---
UID: NF:ntifs.FsRtlAllocateExtraCreateParameterFromLookasideList
title: FsRtlAllocateExtraCreateParameterFromLookasideList function
author: windows-driver-content
description: The FsRtlAllocateExtraCreateParameterFromLookasideList routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure, and generates a pointer to that structure.
old-location: ifsk\fsrtlallocateextracreateparameterfromlookasidelist.htm
old-project: ifsk
ms.assetid: 6dd1aa9d-58e6-484b-b372-4c1d9f6d04f3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntifs/FsRtlAllocateExtraCreateParameterFromLookasideList, ifsk.fsrtlallocateextracreateparameterfromlookasidelist, FsRtlAllocateExtraCreateParameterFromLookasideList, fsrtlref_c85ee3ff-e71f-4c6e-bc37-4187cad9855f.xml, FsRtlAllocateExtraCreateParameterFromLookasideList routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: FsRtlAllocateExtraCreateParameterFromLookasideList is available starting with Windows Vista.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlAllocateExtraCreateParameterFromLookasideList
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAllocateExtraCreateParameterFromLookasideList function


## -description


The <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure, and generates a pointer to that structure.


## -syntax


````
NTSTATUS FsRtlAllocateExtraCreateParameterFromLookasideList(
  _In_     LPCGUID                                        EcpType,
  _In_     ULONG                                          SizeOfContext,
  _In_     FSRTL_ALLOCATE_ECP_FLAGS                       Flags,
  _In_opt_ PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK CleanupCallback,
  _Inout_  PVOID                                          LookasideList,
  _Out_    PVOID                                          *EcpContext
);
````


## -parameters




### -param EcpType [in]

Pointer to a GUID that indicates the type of ECP for whicha context structure should be allocated. For more information about ECPs, see <a href="https://msdn.microsoft.com/e32aeec6-1a0a-4d21-8358-89d9fc0a15eb">Using Extra Create Parameters with an IRP_MJ_CREATE Operation</a>.


### -param SizeOfContext [in]

The size, in bytes, of the ECP context structure. 


### -param Flags [in]

Defines pool allocation options. If the value of the <i>SizeOfContext</i> parameter is larger than the size, in bytes, of the lookaside list that the <i>LookasideList</i> parameter points to, <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> allocates the ECP context structure from system pool instead of the lookaside list. In this case, if the <i>Flags</i> parameter contains the FSRTL_ALLOCATE_ECP_FLAG_CHARGE_QUOTA bit flag value, system pool allocated by <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> is charged against the current process' memory quota. For more information about bit flag values, see the <i>Flags</i> parameter of <a href="..\ntifs\nf-ntifs-fsrtlallocateextracreateparameter.md">FsRtlAllocateExtraCreateParameter</a>. In the more typical case, when <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> allocates memory for the ECP context structure from the lookaside list, <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> ignores the FSRTL_ALLOCATE_ECP_FLAG_CHARGE_QUOTA bit flag. 


### -param CleanupCallback [in, optional]

Optional pointer to a minifilter-defined cleanup callback routine of type <a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>. The cleanup callback routine is called when the ECP context structure is deleted. Set this parameter to <b>NULL</b> if a cleanup callback routine is not applicable.


### -param LookasideList [in, out]

Pointer to an initialized lookaside list from which <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> attempts to allocate pool (for the ECP context structure). To initialize the lookaside list, use the <a href="..\ntifs\nf-ntifs-fsrtlinitextracreateparameterlookasidelist.md">FsRtlInitExtraCreateParameterLookasideList</a> routine. 


### -param EcpContext [out]

Pointer to a location that receives a pointer to the allocated ECP context structure. If <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> failed to allocate sufficient pool for the ECP context structure, <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> sets <i>EcpContext </i>to <b>NULL</b> and returns status code STATUS_INSUFFICIENT_RESOURCES.


## -returns



The <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> routine can return one of the following values:

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
The <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> routine was unable to allocate sufficient memory for an ECP context structure. In this case, the <i>EcpContext </i>parameter is <b>NULL</b>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The ECP context structure was successfully allocated. In this case, <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> returns a pointer to the allocated structure in the <i>EcpContext </i>parameter. 

</td>
</tr>
</table>
 




## -remarks



Use the <a href="..\ntifs\nf-ntifs-fsrtlinitextracreateparameterlookasidelist.md">FsRtlInitExtraCreateParameterLookasideList</a> routine to initialize a paged or nonpaged pool lookaside list. Use the <b>FsRtlAllocateExtraCreateParameterFromLookasideList</b> routine to allocate an ECP context structure from the lookaside list, and the <a href="..\ntifs\nf-ntifs-fsrtlfreeextracreateparameter.md">FsRtlFreeExtraCreateParameter</a> routine to deallocate the ECP context structure.

Use the <a href="..\ntifs\nf-ntifs-fsrtldeleteextracreateparameterlookasidelist.md">FsRtlDeleteExtraCreateParameterLookasideList</a> routine to free a lookaside list.

Drivers must free all ECP context structures and lookaside lists they create before unloading.

For more information about using lookaside lists with drivers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.




## -see-also

<a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>



<a href="..\ntifs\nf-ntifs-fsrtlinitextracreateparameterlookasidelist.md">FsRtlInitExtraCreateParameterLookasideList</a>



<a href="..\ntifs\nf-ntifs-fsrtlinitextracreateparameterlookasidelist.md">FsRtlInitExtraCreateParameterLookasideList</a>



<a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAllocateExtraCreateParameterFromLookasideList routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

