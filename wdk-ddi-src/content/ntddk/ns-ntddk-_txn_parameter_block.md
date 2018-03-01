---
UID: NS:ntddk._TXN_PARAMETER_BLOCK
title: "_TXN_PARAMETER_BLOCK"
author: windows-driver-content
description: The TXN_PARAMETER_BLOCK structure contains information about a transacted file operation.
old-location: ifsk\txn_parameter_block.htm
old-project: ifsk
ms.assetid: 973f440a-ba17-466a-a9f4-f21c07e854d8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PTXN_PARAMETER_BLOCK, PTXN_PARAMETER_BLOCK, PTXN_PARAMETER_BLOCK structure pointer [Installable File System Drivers], TXN_PARAMETER_BLOCK, TXN_PARAMETER_BLOCK structure [Installable File System Drivers], _TXN_PARAMETER_BLOCK, fileinformationstructures_fd9a870c-f8bf-4a9d-8f7c-1dfbdcbab7aa.xml, ifsk.txn_parameter_block, ntddk/PTXN_PARAMETER_BLOCK, ntddk/_TXN_PARAMETER_BLOCK"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: The TXN_PARAMETER_BLOCK structure is available on Windows Vista and later Windows operating systems.
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
-	Ntddk.h
api_name:
-	TXN_PARAMETER_BLOCK
product: Windows
targetos: Windows
req.typenames: TXN_PARAMETER_BLOCK, *PTXN_PARAMETER_BLOCK
---

# _TXN_PARAMETER_BLOCK structure


## -description


The TXN_PARAMETER_BLOCK structure contains information about a transacted file operation. 


## -syntax


````
typedef struct _TXN_PARAMETER_BLOCK {
  USHORT Length;
  USHORT TxFsContext;
  PVOID  TransactionObject;
} TXN_PARAMETER_BLOCK, *PTXN_PARAMETER_BLOCK;
````


## -struct-fields




### -field Length

The size, in bytes, of the TXN_PARAMETER_BLOCK structure. 


### -field TxFsContext

The miniversion ID for the file. 


### -field TransactionObject

An opaque pointer to the transaction object for the transaction. 


## -remarks



A <i>miniversion</i> is a version of a file that a transacted writer creates during a transaction. (A <i>transacted writer</i> is a transacted file handle opened with any permission that is not part of generic read access, but is part of generic write access.) 

If a specific miniversion number for the file is not provided, the <b>TxFsContext</b> member must be set to TXF_MINIVERSION_DEFAULT_VIEW.

The <b>TxFsContext</b> member of the <b>TXN_PARAMETER_BLOCK</b> uses TXF_MINIVERSION_DEFAULT_VIEW to get the default view of the requested file that is based on the value of the <b>TransactionObject</b> member.  So if <b>TransactionObject</b> is the same transaction that has the requested file locked for transacted modification, the caller can see those modifications (the "dirty" view of the file) if the caller can specify the value of the <b>TransactionObject</b> member.  If <b>TransactionObject</b> is not the same transaction that has the requested file locked for transacted modification, the caller gets a transactionally isolated view of the file if it specifies this value.  

A miniversion exists only as a point-in-time view of a file and has not yet been written as an actual on-disk variant of a given file.  A transacted writer creates a miniversion by using the <a href="http://go.microsoft.com/fwlink/p/?linkid=139790">FSCTL_TXFS_CREATE_MINIVERSION</a> control code to call <a href="..\ntifs\nf-ntifs-zwfscontrolfile.md">ZwFsControlFile</a>.  In response, the system creates a miniversion and returns its miniversion ID.  The transacted writer can continue to make changes to the file thereafter.  If the file is opened later by using the returned miniversion ID as the <b>TxFsContext</b> member of the <b>TXN_PARAMETER_BLOCK</b> structure, the resulting file handle shows the file as it was at the time that miniversion was created.

All miniversions created in a transaction go away when the transaction ends.  Afterwards, the file can no longer be opened by using the miniversion IDs.

<div class="alert"><b>Note</b>    A miniversion is available only to the transacted writer that created the miniversion, not to a transacted reader or non-transacted reader.</div>
<div> </div>
The <a href="..\ntddk\nf-ntddk-iogettransactionparameterblock.md">IoGetTransactionParameterBlock</a> routine returns a pointer to this structure. 




## -see-also

<a href="http://go.microsoft.com/fwlink/p/?linkid=139790">FSCTL_TXFS_CREATE_MINIVERSION</a>



<a href="..\ntddk\nf-ntddk-iogettransactionparameterblock.md">IoGetTransactionParameterBlock</a>



<a href="..\ntifs\nf-ntifs-zwfscontrolfile.md">ZwFsControlFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TXN_PARAMETER_BLOCK structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

