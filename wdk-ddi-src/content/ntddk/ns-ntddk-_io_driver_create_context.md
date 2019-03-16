---
UID: NS:ntddk._IO_DRIVER_CREATE_CONTEXT
title: _IO_DRIVER_CREATE_CONTEXT (ntddk.h)
description: The IO_DRIVER_CREATE_CONTEXT structure is used to pass additional parameters to the IoCreateFileEx and FltCreateFileEx2 routines.
old-location: ifsk\io_driver_create_context.htm
tech.root: ifsk
ms.assetid: c2d10f76-5587-4855-9a02-fa7656a3805e
ms.date: 04/16/2018
ms.keywords: "*PIO_DRIVER_CREATE_CONTEXT, IO_DRIVER_CREATE_CONTEXT, IO_DRIVER_CREATE_CONTEXT structure [Installable File System Drivers], PIO_DRIVER_CREATE_CONTEXT, PIO_DRIVER_CREATE_CONTEXT structure pointer [Installable File System Drivers], _IO_DRIVER_CREATE_CONTEXT, fileinformationstructures_d5939ca3-7c95-4788-bec9-b2d4cc7dd45b.xml, ifsk.io_driver_create_context, ntddk/IO_DRIVER_CREATE_CONTEXT, ntddk/PIO_DRIVER_CREATE_CONTEXT"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows Vista.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- IO_DRIVER_CREATE_CONTEXT
product:
- Windows
targetos: Windows
req.typenames: IO_DRIVER_CREATE_CONTEXT, *PIO_DRIVER_CREATE_CONTEXT
---

# _IO_DRIVER_CREATE_CONTEXT structure


## -description


The IO_DRIVER_CREATE_CONTEXT structure is used to pass additional parameters to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a> routines. This structure is optional.
<div class="alert"><b>Note</b>    The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a> routine is used by legacy filter drivers and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a> routine is used by minifilter drivers.</div><div> </div>

## -struct-fields




### -field Size

A read-only member initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548419">IoInitializeDriverCreateContext</a> routine.


### -field ExtraCreateParameter

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a> structure, which contains a list of extra create parameter (ECP) entries.  See the following Remarks section for important information.


### -field DeviceObjectHint

If IO_DRIVER_CREATE_CONTEXT is being used to pass additional create parameters to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a> routine, this member must be <b>NULL</b>.

If IO_DRIVER_CREATE_CONTEXT is being used to pass additional create parameters to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a> routine, this member is a pointer to the device object to which the create request will be sent. The device object must be a legacy filter or file system device object in the file system driver stack for the volume on which the file or directory resides. In the <b>IoCreateFileEx</b> case, this parameter is optional and can be <b>NULL</b>. If this parameter is <b>NULL</b>, the request will be sent to the device object at the top of the driver stack.


### -field TxnParameters

A pointer to a transaction that you want to associate with the create operation. The create operation will be part of the transaction if the value of this member is a valid pointer to the transaction. If the value of this member is <b>NULL</b>, the create operation will not be part of a transaction.


### -field SiloContext

The container that the file resides on. <b>This member was introduced in Windows 10, version 1607</b>.


## -remarks



The IO_DRIVER_CREATE_CONTEXT structure can be allocated from paged or nonpaged pool. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548419">IoInitializeDriverCreateContext</a> routine must initialize the IO_DRIVER_CREATE_CONTEXT structure before the structure can be used. 

The members of the IO_DRIVER_CREATE_CONTEXT structure (excluding the <b>Size</b> member) function as additional parameters to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a> routines.  Relative to the <b>IoCreateFileEx</b> and <b>FltCreateFileEx2</b> routine's interface, the following information may be helpful:

<ul>
<li>
An ECP_LIST structure contains a list of extra create parameter (ECP) entries.  Each ECP entry (ECP context structure) in the ECP list (ECP_LIST structure) functions as an additional create parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>.

To specify an ECP as part of a create operation, initialize the <b>ExtraCreateParameter</b> member of the IO_DRIVER_CREATE_CONTEXT structure with the correct routine:

<ul>
<li> For legacy filter drivers, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545632">FsRtlAllocateExtraCreateParameterList</a> routine must be used to allocate memory pool for the ECP_LIST structure.  The operating system does not automatically free ECP_LIST structures. Instead, once the ECP_LIST structure is allocated, it must eventually be freed by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546005">FsRtlFreeExtraCreateParameterList</a> routine.</li>
<li> For minifilter drivers, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541741">FltAllocateExtraCreateParameterList</a> routine must be used to allocate memory pool for the ECP_LIST structure.  The operating system does not automatically free ECP_LIST structures. Instead, once the ECP_LIST structure is allocated, it must eventually be freed by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542964">FltFreeExtraCreateParameterList</a> routine.</li>
</ul>
If ECPs are used, they must be created, manipulated, and freed by using the appropriate routines.  For example, minifilter drivers use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a> routine to insert an ECP entry into an ECP list.  The following See Also section lists many of these required routines.

Upon return from a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>, the ECP list is unchanged and can be passed to additional <b>IoCreateFileEx</b> or <b>FltCreateFileEx2</b> calls for new create operations.

</li>
<li>
 To create or open a file in the context of a transaction, set the <b>TxnParameters</b> member of the IO_DRIVER_CREATE_CONTEXT structure to the value returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548412">IoGetTransactionParameterBlock</a> routine.  For more information regarding transactions, see <a href="https://go.microsoft.com/fwlink/p/?linkid=66161">Transaction Management (TxF)</a>.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541741">FltAllocateExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542964">FltFreeExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545632">FsRtlAllocateExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546005">FsRtlFreeExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548289">IoCreateFileSpecifyDeviceObjectHint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548412">IoGetTransactionParameterBlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548419">IoInitializeDriverCreateContext</a>
 

 

