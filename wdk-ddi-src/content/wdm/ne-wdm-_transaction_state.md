---
UID: NE:wdm._TRANSACTION_STATE
title: _TRANSACTION_STATE (wdm.h)
description: The TRANSACTION_STATE enumeration defines the states that KTM can assign to a transaction.
old-location: kernel\transaction_state.htm
tech.root: kernel
ms.assetid: b97bedc5-6393-49bd-b803-e70e3a3d49df
ms.date: 04/30/2018
keywords: ["TRANSACTION_STATE enumeration"]
ms.keywords: TRANSACTION_STATE, TRANSACTION_STATE enumeration [Kernel-Mode Driver Architecture], TransactionStateCommittedNotify, TransactionStateIndoubt, TransactionStateNormal, _TRANSACTION_STATE, kernel.transaction_state, ktm_ref_051131c5-e3a5-430e-afca-053fcb68f746.xml, wdm/TRANSACTION_STATE, wdm/TransactionStateCommittedNotify, wdm/TransactionStateIndoubt, wdm/TransactionStateNormal
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
req.typenames: TRANSACTION_STATE
f1_keywords:
 - _TRANSACTION_STATE
 - wdm/_TRANSACTION_STATE
 - TRANSACTION_STATE
 - wdm/TRANSACTION_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - TRANSACTION_STATE
---

# _TRANSACTION_STATE enumeration


## -description

The <b>TRANSACTION_STATE</b> enumeration defines the states that KTM can assign to a transaction.

## -enum-fields

### -field TransactionStateNormal

The transaction's state is neither in doubt nor committed.

### -field TransactionStateIndoubt

The transaction's state is in doubt (that is, KTM cannot determine whether the transaction should be committed or rolled back). A transaction that has been prepared enters the "in doubt" state if its <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">superior transaction manager</a> becomes unavailable.

### -field TransactionStateCommittedNotify

The transaction has been committed. Commit notifications might (or might not) have been delivered to all enlistments.

## -remarks

The <b>TRANSACTION_STATE</b> enumeration is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a>

