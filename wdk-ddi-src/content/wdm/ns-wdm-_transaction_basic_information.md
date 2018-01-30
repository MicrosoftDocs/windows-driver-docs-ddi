---
UID: NS:wdm._TRANSACTION_BASIC_INFORMATION
title: "_TRANSACTION_BASIC_INFORMATION"
author: windows-driver-content
description: The TRANSACTION_BASIC_INFORMATION structure contains information about a transaction object.
old-location: kernel\transaction_basic_information.htm
old-project: kernel
ms.assetid: 79dd9ff3-2a5f-457a-8a8a-4963a799055c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: TRANSACTION_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], wdm/PTRANSACTION_BASIC_INFORMATION, kernel.transaction_basic_information, PTRANSACTION_BASIC_INFORMATION, PTRANSACTION_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _TRANSACTION_BASIC_INFORMATION, ktm_ref_3246b7cb-244e-4772-b3ca-bfd69e973f12.xml, wdm/TRANSACTION_BASIC_INFORMATION, TRANSACTION_BASIC_INFORMATION, *PTRANSACTION_BASIC_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	TRANSACTION_BASIC_INFORMATION
product: Windows
targetos: Windows
req.typenames: TRANSACTION_BASIC_INFORMATION, *PTRANSACTION_BASIC_INFORMATION
req.product: Windows 10 or later.
---

# _TRANSACTION_BASIC_INFORMATION structure


## -description


The <b>TRANSACTION_BASIC_INFORMATION</b> structure contains information about a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>.


## -syntax


````
typedef struct _TRANSACTION_BASIC_INFORMATION {
  GUID  TransactionId;
  ULONG State;
  ULONG Outcome;
} TRANSACTION_BASIC_INFORMATION, *PTRANSACTION_BASIC_INFORMATION;
````


## -struct-fields




### -field TransactionId

A GUID that KTM has assigned to the transaction object. This value is also known as the transaction's <a href="https://msdn.microsoft.com/927a417b-35f5-49b8-85f3-7e6b1f5c0225">unit of work (UOW) identifier</a>.


### -field State

A <a href="..\wdm\ne-wdm-_transaction_state.md">TRANSACTION_STATE</a>-typed value that specifies the transaction's current state.


### -field Outcome

A <a href="..\wdm\ne-wdm-_transaction_outcome.md">TRANSACTION_OUTCOME</a>-typed value that specifies the transaction's outcome (result).


## -remarks


The <b>TRANSACTION_BASIC_INFORMATION</b> structure is used with the <a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a> routine. This routine fills in the structure's members.



## -see-also

<a href="..\wdm\ne-wdm-_transaction_state.md">TRANSACTION_STATE</a>

<a href="..\wdm\ne-wdm-_transaction_information_class.md">TRANSACTION_INFORMATION_CLASS</a>

<a href="..\wdm\ne-wdm-_transaction_outcome.md">TRANSACTION_OUTCOME</a>

<a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a>

<a href="..\wdm\nf-wdm-tmgettransactionid.md">TmGetTransactionId</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TRANSACTION_BASIC_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

