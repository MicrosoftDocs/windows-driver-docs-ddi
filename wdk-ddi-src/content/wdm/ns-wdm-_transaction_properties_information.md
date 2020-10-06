---
UID: NS:wdm._TRANSACTION_PROPERTIES_INFORMATION
title: _TRANSACTION_PROPERTIES_INFORMATION (wdm.h)
description: The TRANSACTION_PROPERTIES_INFORMATION structure contains a transaction object's properties.
old-location: kernel\transaction_properties_information.htm
tech.root: kernel
ms.assetid: 76b0f102-0d09-4b16-b8e1-727a3a6e48c9
ms.date: 04/30/2018
keywords: ["TRANSACTION_PROPERTIES_INFORMATION structure"]
ms.keywords: "*PTRANSACTION_PROPERTIES_INFORMATION, PTRANSACTION_PROPERTIES_INFORMATION, PTRANSACTION_PROPERTIES_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTION_PROPERTIES_INFORMATION, TRANSACTION_PROPERTIES_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTION_PROPERTIES_INFORMATION, kernel.transaction_properties_information, ktm_ref_bc17351c-f0ea-457e-968c-19785c0afd8d.xml, wdm/PTRANSACTION_PROPERTIES_INFORMATION, wdm/TRANSACTION_PROPERTIES_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.typenames: TRANSACTION_PROPERTIES_INFORMATION, *PTRANSACTION_PROPERTIES_INFORMATION
f1_keywords:
 - _TRANSACTION_PROPERTIES_INFORMATION
 - wdm/_TRANSACTION_PROPERTIES_INFORMATION
 - PTRANSACTION_PROPERTIES_INFORMATION
 - wdm/PTRANSACTION_PROPERTIES_INFORMATION
 - TRANSACTION_PROPERTIES_INFORMATION
 - wdm/TRANSACTION_PROPERTIES_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - TRANSACTION_PROPERTIES_INFORMATION
---

# _TRANSACTION_PROPERTIES_INFORMATION structure


## -description

The <b>TRANSACTION_PROPERTIES_INFORMATION</b> structure contains a <a href="/windows-hardware/drivers/kernel/transaction-objects">transaction object's</a> properties.

## -struct-fields

### -field IsolationLevel

Reserved for future use.

### -field IsolationFlags

Reserved for future use.

### -field Timeout

A time-out value. If the transaction has not been committed by the time specified by this parameter, KTM rolls back the transaction. The time-out value is expressed in system time units (100-nanosecond intervals), and can specify either an absolute time or a relative time. If the value of the <b>Timeout</b> member is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. Set this member to zero if no time-out is required. If <b>Timeout</b> is zero, the transaction never times out.

### -field Outcome

A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_transaction_outcome">TRANSACTION_OUTCOME</a>-typed value that identifies the transaction's outcome (result). You can obtain this value by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a>, but you cannot set the value with <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationtransaction">ZwSetInformationTransaction</a>.

### -field DescriptionLength

The size, in bytes, of the buffer that contains the <b>Description</b> member's array.

### -field Description

A caller-allocated array of characters that contains or receives the transaction's description string. The <a href="/windows-hardware/drivers/kernel/creating-a-transactional-client">TPS client</a> can specify this string when it calls <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a>. The client can retrieve the string by calling by calling <b>ZwQueryInformationTransaction</b>, and it can modify the string by calling <b>ZwSetInformationTransaction</b>.

## -remarks

The <b>TRANSACTION_PROPERTIES_INFORMATION</b> structure is used with the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationtransaction">ZwSetInformationTransaction</a> routines.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_transaction_information_class">TRANSACTION_INFORMATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_transaction_outcome">TRANSACTION_OUTCOME</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransaction">ZwCreateTransaction</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationtransaction">ZwSetInformationTransaction</a>