---
UID: NS:ntddk._IO_DRIVER_CREATE_CONTEXT
title: "_IO_DRIVER_CREATE_CONTEXT"
author: windows-driver-content
description: The IO_DRIVER_CREATE_CONTEXT structure is used to pass additional parameters to the IoCreateFileEx and FltCreateFileEx2 routines.
old-location: ifsk\io_driver_create_context.htm
old-project: ifsk
ms.assetid: c2d10f76-5587-4855-9a02-fa7656a3805e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PIO_DRIVER_CREATE_CONTEXT, IO_DRIVER_CREATE_CONTEXT, IO_DRIVER_CREATE_CONTEXT structure [Installable File System Drivers], PIO_DRIVER_CREATE_CONTEXT, PIO_DRIVER_CREATE_CONTEXT structure pointer [Installable File System Drivers], _IO_DRIVER_CREATE_CONTEXT, fileinformationstructures_d5939ca3-7c95-4788-bec9-b2d4cc7dd45b.xml, ifsk.io_driver_create_context, ntddk/IO_DRIVER_CREATE_CONTEXT, ntddk/PIO_DRIVER_CREATE_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	IO_DRIVER_CREATE_CONTEXT
product: Windows
targetos: Windows
req.typenames: IO_DRIVER_CREATE_CONTEXT, *PIO_DRIVER_CREATE_CONTEXT
---

# _IO_DRIVER_CREATE_CONTEXT structure


## -description


The IO_DRIVER_CREATE_CONTEXT structure is used to pass additional parameters to the <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> and <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> routines. This structure is optional.
<div class="alert"><b>Note</b>    The <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> routine is used by legacy filter drivers and the <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> routine is used by minifilter drivers.</div><div> </div>

## -syntax


````
typedef struct _IO_DRIVER_CREATE_CONTEXT {
  CSHORT               Size;
  struct _ECP_LIST  *ExtraCreateParameter;
  PVOID                DeviceObjectHint;
  PTXN_PARAMETER_BLOCK TxnParameters;
  PESILO               SiloContext;
} IO_DRIVER_CREATE_CONTEXT, *PIO_DRIVER_CREATE_CONTEXT;
````


## -struct-fields




### -field Size

A read-only member initialized by the <a href="..\ntddk\nf-ntddk-ioinitializedrivercreatecontext.md">IoInitializeDriverCreateContext</a> routine.


### -field ExtraCreateParameter

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a> structure, which contains a list of extra create parameter (ECP) entries.  See the following Remarks section for important information.


### -field DeviceObjectHint

If IO_DRIVER_CREATE_CONTEXT is being used to pass additional create parameters to the <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> routine, this member must be <b>NULL</b>.

If IO_DRIVER_CREATE_CONTEXT is being used to pass additional create parameters to the <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> routine, this member is a pointer to the device object to which the create request will be sent. The device object must be a legacy filter or file system device object in the file system driver stack for the volume on which the file or directory resides. In the <b>IoCreateFileEx</b> case, this parameter is optional and can be <b>NULL</b>. If this parameter is <b>NULL</b>, the request will be sent to the device object at the top of the driver stack.


### -field TxnParameters

A pointer to a transaction that you want to associate with the create operation. The create operation will be part of the transaction if the value of this member is a valid pointer to the transaction. If the value of this member is <b>NULL</b>, the create operation will not be part of a transaction.


### -field SiloContext

The container that the file resides on. <b>This member was introduced in Windows 10, version 1607</b>.


## -remarks



The IO_DRIVER_CREATE_CONTEXT structure can be allocated from paged or nonpaged pool. The <a href="..\ntddk\nf-ntddk-ioinitializedrivercreatecontext.md">IoInitializeDriverCreateContext</a> routine must initialize the IO_DRIVER_CREATE_CONTEXT structure before the structure can be used. 

The members of the IO_DRIVER_CREATE_CONTEXT structure (excluding the <b>Size</b> member) function as additional parameters to the <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> and <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> routines.  Relative to the <b>IoCreateFileEx</b> and <b>FltCreateFileEx2</b> routine's interface, the following information may be helpful:

<ul>
<li>
An ECP_LIST structure contains a list of extra create parameter (ECP) entries.  Each ECP entry (ECP context structure) in the ECP list (ECP_LIST structure) functions as an additional create parameter to <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> and <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>.

To specify an ECP as part of a create operation, initialize the <b>ExtraCreateParameter</b> member of the IO_DRIVER_CREATE_CONTEXT structure with the correct routine:

<ul>
<li> For legacy filter drivers, the <a href="..\ntifs\nf-ntifs-fsrtlallocateextracreateparameterlist.md">FsRtlAllocateExtraCreateParameterList</a> routine must be used to allocate memory pool for the ECP_LIST structure.  The operating system does not automatically free ECP_LIST structures. Instead, once the ECP_LIST structure is allocated, it must eventually be freed by using the <a href="..\ntifs\nf-ntifs-fsrtlfreeextracreateparameterlist.md">FsRtlFreeExtraCreateParameterList</a> routine.</li>
<li> For minifilter drivers, the <a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a> routine must be used to allocate memory pool for the ECP_LIST structure.  The operating system does not automatically free ECP_LIST structures. Instead, once the ECP_LIST structure is allocated, it must eventually be freed by using the <a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a> routine.</li>
</ul>
If ECPs are used, they must be created, manipulated, and freed by using the appropriate routines.  For example, minifilter drivers use the <a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a> routine to insert an ECP entry into an ECP list.  The following See Also section lists many of these required routines.

Upon return from a call to <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> or <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>, the ECP list is unchanged and can be passed to additional <b>IoCreateFileEx</b> or <b>FltCreateFileEx2</b> calls for new create operations.

</li>
<li>
 To create or open a file in the context of a transaction, set the <b>TxnParameters</b> member of the IO_DRIVER_CREATE_CONTEXT structure to the value returned by the <a href="..\ntddk\nf-ntddk-iogettransactionparameterblock.md">IoGetTransactionParameterBlock</a> routine.  For more information regarding transactions, see <a href="http://go.microsoft.com/fwlink/p/?linkid=66161">Transaction Management (TxF)</a>.

</li>
</ul>



## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlfreeextracreateparameterlist.md">FsRtlFreeExtraCreateParameterList</a>



<a href="..\ntddk\nf-ntddk-ioinitializedrivercreatecontext.md">IoInitializeDriverCreateContext</a>



<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="..\ntddk\nf-ntddk-iocreatefilespecifydeviceobjecthint.md">IoCreateFileSpecifyDeviceObjectHint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>



<a href="..\ntddk\nf-ntddk-iogettransactionparameterblock.md">IoGetTransactionParameterBlock</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>



<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>



<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>



<a href="..\ntifs\nf-ntifs-fsrtlallocateextracreateparameterlist.md">FsRtlAllocateExtraCreateParameterList</a>



<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IO_DRIVER_CREATE_CONTEXT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

