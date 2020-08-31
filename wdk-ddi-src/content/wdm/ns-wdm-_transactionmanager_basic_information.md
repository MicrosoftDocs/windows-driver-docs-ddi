---
UID: NS:wdm._TRANSACTIONMANAGER_BASIC_INFORMATION
title: _TRANSACTIONMANAGER_BASIC_INFORMATION (wdm.h)
description: The TRANSACTIONMANAGER_BASIC_INFORMATION structure contains information about a transaction manager object.
old-location: kernel\transactionmanager_basic_information.htm
tech.root: kernel
ms.assetid: bffa1bd2-143c-4d32-a886-0a2e82320dc8
ms.date: 04/30/2018
keywords: ["TRANSACTIONMANAGER_BASIC_INFORMATION structure"]
ms.keywords: "*PTRANSACTIONMANAGER_BASIC_INFORMATION, PTRANSACTIONMANAGER_BASIC_INFORMATION, PTRANSACTIONMANAGER_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTIONMANAGER_BASIC_INFORMATION, TRANSACTIONMANAGER_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTIONMANAGER_BASIC_INFORMATION, kernel.transactionmanager_basic_information, ktm_ref_0b404d6e-efa9-4f37-a14f-4e8fcdc2c6e5.xml, wdm/PTRANSACTIONMANAGER_BASIC_INFORMATION, wdm/TRANSACTIONMANAGER_BASIC_INFORMATION"
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
req.typenames: TRANSACTIONMANAGER_BASIC_INFORMATION, *PTRANSACTIONMANAGER_BASIC_INFORMATION
f1_keywords:
 - _TRANSACTIONMANAGER_BASIC_INFORMATION
 - wdm/_TRANSACTIONMANAGER_BASIC_INFORMATION
 - PTRANSACTIONMANAGER_BASIC_INFORMATION
 - wdm/PTRANSACTIONMANAGER_BASIC_INFORMATION
 - TRANSACTIONMANAGER_BASIC_INFORMATION
 - wdm/TRANSACTIONMANAGER_BASIC_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - TRANSACTIONMANAGER_BASIC_INFORMATION
---

# _TRANSACTIONMANAGER_BASIC_INFORMATION structure


## -description

The <b>TRANSACTIONMANAGER_BASIC_INFORMATION</b> structure contains information about a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-manager-objects">transaction manager object</a>.

## -struct-fields

### -field TmIdentity

A GUID that KTM has assigned to a transaction manager object.

### -field VirtualClock

The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a> that is currently associated with a transaction manager object.

## -remarks

The <b>TRANSACTIONMANAGER_BASIC_INFORMATION</b> structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a> routine.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_transactionmanager_information_class">TRANSACTIONMANAGER_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a>

