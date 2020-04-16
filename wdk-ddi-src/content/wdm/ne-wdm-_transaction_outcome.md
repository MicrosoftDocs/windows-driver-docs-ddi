---
UID: NE:wdm._TRANSACTION_OUTCOME
title: _TRANSACTION_OUTCOME (wdm.h)
description: The TRANSACTION_OUTCOME enumeration defines the outcomes (results) that KTM can assign to a transaction.
old-location: kernel\transaction_outcome.htm
tech.root: kernel
ms.assetid: 1612e8d8-996b-45d2-93cc-df5b388596d4
ms.date: 04/30/2018
keywords: ["_TRANSACTION_OUTCOME enumeration"]
ms.keywords: TRANSACTION_OUTCOME, TRANSACTION_OUTCOME enumeration [Kernel-Mode Driver Architecture], TransactionOutcomeAborted, TransactionOutcomeCommitted, TransactionOutcomeUndetermined, _TRANSACTION_OUTCOME, kernel.transaction_outcome, ktm_ref_e1c01db3-bc06-43d4-a046-f94af84782e8.xml, wdm/TRANSACTION_OUTCOME, wdm/TransactionOutcomeAborted, wdm/TransactionOutcomeCommitted, wdm/TransactionOutcomeUndetermined
f1_keywords:
 - "wdm/TRANSACTION_OUTCOME"
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
- TRANSACTION_OUTCOME
product:
- Windows
targetos: Windows
req.typenames: TRANSACTION_OUTCOME
---

# _TRANSACTION_OUTCOME enumeration


## -description


The <b>TRANSACTION_OUTCOME</b> enumeration defines the outcomes (results) that KTM can assign to a transaction.


## -enum-fields




### -field TransactionOutcomeUndetermined

The transaction has not yet been committed or rolled back.


### -field TransactionOutcomeCommitted

The transaction has been committed.


### -field TransactionOutcomeAborted

The transaction has been rolled back.


## -remarks



The <b>TRANSACTION_OUTCOME</b> enumeration is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a>
 

 

