---
UID: NS:wdm._TRANSACTION_ENLISTMENT_PAIR
title: _TRANSACTION_ENLISTMENT_PAIR (wdm.h)
description: The TRANSACTION_ENLISTMENT_PAIR structure contains information about an enlistment that is associated with a transaction object.
old-location: kernel\transaction_enlistment_pair.htm
tech.root: kernel
ms.assetid: f8d49d61-f15e-4972-bcd2-d20f1be5786c
ms.date: 04/30/2018
keywords: ["TRANSACTION_ENLISTMENT_PAIR structure"]
ms.keywords: "*PTRANSACTION_ENLISTMENT_PAIR, PTRANSACTION_ENLISTMENT_PAIR, PTRANSACTION_ENLISTMENT_PAIR structure pointer [Kernel-Mode Driver Architecture], TRANSACTION_ENLISTMENT_PAIR, TRANSACTION_ENLISTMENT_PAIR structure [Kernel-Mode Driver Architecture], _TRANSACTION_ENLISTMENT_PAIR, kernel.transaction_enlistment_pair, ktm_ref_5f4d1426-1829-4c3d-836f-8655b41d9c0c.xml, wdm/PTRANSACTION_ENLISTMENT_PAIR, wdm/TRANSACTION_ENLISTMENT_PAIR"
f1_keywords:
 - "wdm/TRANSACTION_ENLISTMENT_PAIR"
 - "TRANSACTION_ENLISTMENT_PAIR"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- TRANSACTION_ENLISTMENT_PAIR
targetos: Windows
req.typenames: TRANSACTION_ENLISTMENT_PAIR, *PTRANSACTION_ENLISTMENT_PAIR
---

# _TRANSACTION_ENLISTMENT_PAIR structure


## -description


The <b>TRANSACTION_ENLISTMENT_PAIR</b> structure contains information about an enlistment that is associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-objects">transaction object</a>.


## -struct-fields




### -field EnlistmentId

A GUID that KTM has assigned to the enlistment.


### -field ResourceManagerId

A GUID that KTM has assigned to the resource manager that created the enlistment.


## -remarks



The <b>TRANSACTION_ENLISTMENT_PAIR</b> structure is used as a member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_enlistments_information">TRANSACTION_ENLISTMENTS_INFORMATION</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_enlistments_information">TRANSACTION_ENLISTMENTS_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a>
 

 

