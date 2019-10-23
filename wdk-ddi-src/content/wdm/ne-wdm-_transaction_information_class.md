---
UID: NE:wdm._TRANSACTION_INFORMATION_CLASS
title: _TRANSACTION_INFORMATION_CLASS (wdm.h)
description: The TRANSACTION_INFORMATION_CLASS enumeration specifies the type of information that ZwSetInformationTransaction can set and ZwQueryInformationTransaction can retrieve for a transaction manager object.
old-location: kernel\transaction_information_class.htm
tech.root: kernel
ms.assetid: f3211114-8924-4e57-85a3-12471585652b
ms.date: 04/30/2018
ms.keywords: TRANSACTION_INFORMATION_CLASS, TRANSACTION_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], TransactionBasicInformation, TransactionEnlistmentInformation, TransactionPropertiesInformation, TransactionSuperiorEnlistmentInformation, _TRANSACTION_INFORMATION_CLASS, kernel.transaction_information_class, ktm_ref_b02f7265-fb29-402a-b0d3-79427735f354.xml, wdm/TRANSACTION_INFORMATION_CLASS, wdm/TransactionBasicInformation, wdm/TransactionEnlistmentInformation, wdm/TransactionPropertiesInformation, wdm/TransactionSuperiorEnlistmentInformation
ms.topic: enum
f1_keywords:
 - "wdm/TRANSACTION_INFORMATION_CLASS"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
- TRANSACTION_INFORMATION_CLASS
product:
- Windows
targetos: Windows
req.typenames: TRANSACTION_INFORMATION_CLASS
---

# _TRANSACTION_INFORMATION_CLASS enumeration


## -description


The <b>TRANSACTION_INFORMATION_CLASS</b> enumeration specifies the type of information that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationtransaction">ZwSetInformationTransaction</a> can set and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a> can retrieve for a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-manager-objects">transaction manager object</a>.


## -enum-fields




### -field TransactionBasicInformation

Information about a transaction manager object is stored in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_basic_information">TRANSACTION_BASIC_INFORMATION</a> structure.


### -field TransactionPropertiesInformation

Information about a transaction manager object is stored in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_properties_information">TRANSACTION_PROPERTIES_INFORMATION</a> structure.


### -field TransactionEnlistmentInformation

Information about a transaction manager object is stored in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_transaction_enlistments_information">TRANSACTION_ENLISTMENTS_INFORMATION</a> structure.


### -field TransactionSuperiorEnlistmentInformation

Information about a transaction manager object is stored in a <b>TRANSACTION_SUPERIOR_ENLISTMENT_INFORMATION</b> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransaction">ZwQueryInformationTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationtransaction">ZwSetInformationTransaction</a>
 

 

