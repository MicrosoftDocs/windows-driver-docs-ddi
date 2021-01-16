---
UID: NS:wdm._TRANSACTION_ENLISTMENTS_INFORMATION
title: _TRANSACTION_ENLISTMENTS_INFORMATION (wdm.h)
description: The TRANSACTION_ENLISTMENTS_INFORMATION structure contains information about the enlistments that are associated with a transaction object.
old-location: kernel\transaction_enlistments_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["TRANSACTION_ENLISTMENTS_INFORMATION structure"]
ms.keywords: "*PTRANSACTION_ENLISTMENTS_INFORMATION, PTRANSACTION_ENLISTMENTS_INFORMATION, PTRANSACTION_ENLISTMENTS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTION_ENLISTMENTS_INFORMATION, TRANSACTION_ENLISTMENTS_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTION_ENLISTMENTS_INFORMATION, kernel.transaction_enlistments_information, ktm_ref_d6790593-2057-4d78-82f2-9d4d64cd800c.xml, wdm/PTRANSACTION_ENLISTMENTS_INFORMATION, wdm/TRANSACTION_ENLISTMENTS_INFORMATION"
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
targetos: Windows
req.typenames: TRANSACTION_ENLISTMENTS_INFORMATION, *PTRANSACTION_ENLISTMENTS_INFORMATION
f1_keywords:
 - _TRANSACTION_ENLISTMENTS_INFORMATION
 - wdm/_TRANSACTION_ENLISTMENTS_INFORMATION
 - PTRANSACTION_ENLISTMENTS_INFORMATION
 - wdm/PTRANSACTION_ENLISTMENTS_INFORMATION
 - TRANSACTION_ENLISTMENTS_INFORMATION
 - wdm/TRANSACTION_ENLISTMENTS_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _TRANSACTION_ENLISTMENTS_INFORMATION
 - PTRANSACTION_ENLISTMENTS_INFORMATION
 - TRANSACTION_ENLISTMENTS_INFORMATION
---

# _TRANSACTION_ENLISTMENTS_INFORMATION structure


## -description

The <b>TRANSACTION_ENLISTMENTS_INFORMATION</b> structure contains information about the enlistments that are associated with a <a href="/windows-hardware/drivers/kernel/transaction-objects">transaction object</a>.

## -struct-fields

### -field NumberOfEnlistments

The number of enlistments that are associated with a transaction object. This is also the number of elements in the array that the <b>EnlistmentPair</b> member specifies.

### -field EnlistmentPair

A caller-allocated array of <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_enlistment_pair">TRANSACTION_ENLISTMENT_PAIR</a> structures.

## -remarks

The <b>TRANSACTION_ENLISTMENTS_INFORMATION</b> structure is used with the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a> routine. This routine fills in the structure's members.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_enlistment_pair">TRANSACTION_ENLISTMENT_PAIR</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_transaction_information_class">TRANSACTION_INFORMATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a>

