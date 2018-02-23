---
UID: NS:wdm._TRANSACTION_ENLISTMENTS_INFORMATION
title: "_TRANSACTION_ENLISTMENTS_INFORMATION"
author: windows-driver-content
description: The TRANSACTION_ENLISTMENTS_INFORMATION structure contains information about the enlistments that are associated with a transaction object.
old-location: kernel\transaction_enlistments_information.htm
old-project: kernel
ms.assetid: 8b33a7ed-6892-4b2d-9d7a-cfc43c9fbf68
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: TRANSACTION_ENLISTMENTS_INFORMATION structure [Kernel-Mode Driver Architecture], TRANSACTION_ENLISTMENTS_INFORMATION, ktm_ref_d6790593-2057-4d78-82f2-9d4d64cd800c.xml, wdm/TRANSACTION_ENLISTMENTS_INFORMATION, PTRANSACTION_ENLISTMENTS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PTRANSACTION_ENLISTMENTS_INFORMATION, kernel.transaction_enlistments_information, wdm/PTRANSACTION_ENLISTMENTS_INFORMATION, *PTRANSACTION_ENLISTMENTS_INFORMATION, _TRANSACTION_ENLISTMENTS_INFORMATION
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
-	Wdm.h
apiname:
-	TRANSACTION_ENLISTMENTS_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PTRANSACTION_ENLISTMENTS_INFORMATION, TRANSACTION_ENLISTMENTS_INFORMATION"
req.product: Windows 10 or later.
---

# _TRANSACTION_ENLISTMENTS_INFORMATION structure


## -description


The <b>TRANSACTION_ENLISTMENTS_INFORMATION</b> structure contains information about the enlistments that are associated with a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>.


## -syntax


````
typedef struct _TRANSACTION_ENLISTMENTS_INFORMATION {
  ULONG                       NumberOfEnlistments;
  TRANSACTION_ENLISTMENT_PAIR EnlistmentPair[1];
} TRANSACTION_ENLISTMENTS_INFORMATION, *PTRANSACTION_ENLISTMENTS_INFORMATION;
````


## -struct-fields




### -field NumberOfEnlistments

The number of enlistments that are associated with a transaction object. This is also the number of elements in the array that the <b>EnlistmentPair</b> member specifies.


### -field EnlistmentPair

A caller-allocated array of <a href="..\wdm\ns-wdm-_transaction_enlistment_pair.md">TRANSACTION_ENLISTMENT_PAIR</a> structures. 


## -remarks



The <b>TRANSACTION_ENLISTMENTS_INFORMATION</b> structure is used with the <a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a> routine. This routine fills in the structure's members.




## -see-also

<a href="..\wdm\ns-wdm-_transaction_enlistment_pair.md">TRANSACTION_ENLISTMENT_PAIR</a>



<a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a>



<a href="..\wdm\ne-wdm-_transaction_information_class.md">TRANSACTION_INFORMATION_CLASS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TRANSACTION_ENLISTMENTS_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

