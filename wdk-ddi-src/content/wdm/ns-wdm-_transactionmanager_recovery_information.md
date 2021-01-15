---
UID: NS:wdm._TRANSACTIONMANAGER_RECOVERY_INFORMATION
title: _TRANSACTIONMANAGER_RECOVERY_INFORMATION (wdm.h)
description: The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure contains information about a transaction manager object.
old-location: kernel\transactionmanager_recovery_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["TRANSACTIONMANAGER_RECOVERY_INFORMATION structure"]
ms.keywords: "*PTRANSACTIONMANAGER_RECOVERY_INFORMATION, PTRANSACTIONMANAGER_RECOVERY_INFORMATION, PTRANSACTIONMANAGER_RECOVERY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTIONMANAGER_RECOVERY_INFORMATION, TRANSACTIONMANAGER_RECOVERY_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTIONMANAGER_RECOVERY_INFORMATION, kernel.transactionmanager_recovery_information, ktm_ref_9efce7e2-3965-4659-8659-4f8262aad962.xml, wdm/PTRANSACTIONMANAGER_RECOVERY_INFORMATION, wdm/TRANSACTIONMANAGER_RECOVERY_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
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
req.typenames: TRANSACTIONMANAGER_RECOVERY_INFORMATION, *PTRANSACTIONMANAGER_RECOVERY_INFORMATION
f1_keywords:
 - _TRANSACTIONMANAGER_RECOVERY_INFORMATION
 - wdm/_TRANSACTIONMANAGER_RECOVERY_INFORMATION
 - PTRANSACTIONMANAGER_RECOVERY_INFORMATION
 - wdm/PTRANSACTIONMANAGER_RECOVERY_INFORMATION
 - TRANSACTIONMANAGER_RECOVERY_INFORMATION
 - wdm/TRANSACTIONMANAGER_RECOVERY_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _TRANSACTIONMANAGER_RECOVERY_INFORMATION
 - PTRANSACTIONMANAGER_RECOVERY_INFORMATION
 - TRANSACTIONMANAGER_RECOVERY_INFORMATION
---

# _TRANSACTIONMANAGER_RECOVERY_INFORMATION structure


## -description

The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure contains information about a <a href="/windows-hardware/drivers/kernel/transaction-manager-objects">transaction manager object</a>.

## -struct-fields

### -field LastRecoveredLsn

The last <a href="/windows-hardware/drivers/kernel/clfs-log-sequence-numbers">log sequence number</a> of the last log record that KTM obtained from <a href="/windows-hardware/drivers/kernel/using-common-log-file-system">CLFS</a> during the most recent recovery operation.

## -remarks

The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure is used with the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_transactionmanager_information_class">TRANSACTIONMANAGER_INFORMATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a>

