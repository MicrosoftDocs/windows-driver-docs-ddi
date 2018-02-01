---
UID: NS:wdm._TRANSACTION_ENLISTMENT_PAIR
title: "_TRANSACTION_ENLISTMENT_PAIR"
author: windows-driver-content
description: The TRANSACTION_ENLISTMENT_PAIR structure contains information about an enlistment that is associated with a transaction object.
old-location: kernel\transaction_enlistment_pair.htm
old-project: kernel
ms.assetid: f8d49d61-f15e-4972-bcd2-d20f1be5786c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.transaction_enlistment_pair, ktm_ref_5f4d1426-1829-4c3d-836f-8655b41d9c0c.xml, _TRANSACTION_ENLISTMENT_PAIR, TRANSACTION_ENLISTMENT_PAIR structure [Kernel-Mode Driver Architecture], PTRANSACTION_ENLISTMENT_PAIR, TRANSACTION_ENLISTMENT_PAIR, *PTRANSACTION_ENLISTMENT_PAIR, wdm/PTRANSACTION_ENLISTMENT_PAIR, wdm/TRANSACTION_ENLISTMENT_PAIR, PTRANSACTION_ENLISTMENT_PAIR structure pointer [Kernel-Mode Driver Architecture]
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
-	TRANSACTION_ENLISTMENT_PAIR
product: Windows
targetos: Windows
req.typenames: "*PTRANSACTION_ENLISTMENT_PAIR, TRANSACTION_ENLISTMENT_PAIR"
req.product: Windows 10 or later.
---

# _TRANSACTION_ENLISTMENT_PAIR structure


## -description


The <b>TRANSACTION_ENLISTMENT_PAIR</b> structure contains information about an enlistment that is associated with a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>.


## -syntax


````
typedef struct _TRANSACTION_ENLISTMENT_PAIR {
  GUID EnlistmentId;
  GUID ResourceManagerId;
} TRANSACTION_ENLISTMENT_PAIR, *PTRANSACTION_ENLISTMENT_PAIR;
````


## -struct-fields




### -field EnlistmentId

A GUID that KTM has assigned to the enlistment.


### -field ResourceManagerId

A GUID that KTM has assigned to the resource manager that created the enlistment.


## -remarks


The <b>TRANSACTION_ENLISTMENT_PAIR</b> structure is used as a member of the <a href="..\wdm\ns-wdm-_transaction_enlistments_information.md">TRANSACTION_ENLISTMENTS_INFORMATION</a> structure.



## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a>

<a href="..\wdm\ns-wdm-_transaction_enlistments_information.md">TRANSACTION_ENLISTMENTS_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TRANSACTION_ENLISTMENT_PAIR structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

