---
UID: NE:wdm._TRANSACTION_INFORMATION_CLASS
title: "_TRANSACTION_INFORMATION_CLASS"
author: windows-driver-content
description: The TRANSACTION_INFORMATION_CLASS enumeration specifies the type of information that ZwSetInformationTransaction can set and ZwQueryInformationTransaction can retrieve for a transaction manager object.
old-location: kernel\transaction_information_class.htm
old-project: kernel
ms.assetid: f3211114-8924-4e57-85a3-12471585652b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: TRANSACTION_INFORMATION_CLASS, TRANSACTION_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], TransactionBasicInformation, TransactionEnlistmentInformation, TransactionPropertiesInformation, TransactionSuperiorEnlistmentInformation, _TRANSACTION_INFORMATION_CLASS, kernel.transaction_information_class, ktm_ref_b02f7265-fb29-402a-b0d3-79427735f354.xml, wdm/TRANSACTION_INFORMATION_CLASS, wdm/TransactionBasicInformation, wdm/TransactionEnlistmentInformation, wdm/TransactionPropertiesInformation, wdm/TransactionSuperiorEnlistmentInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	TRANSACTION_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: TRANSACTION_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _TRANSACTION_INFORMATION_CLASS enumeration


## -description


The <b>TRANSACTION_INFORMATION_CLASS</b> enumeration specifies the type of information that <a href="..\wdm\nf-wdm-zwsetinformationtransaction.md">ZwSetInformationTransaction</a> can set and <a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a> can retrieve for a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.


## -syntax


````
typedef enum _TRANSACTION_INFORMATION_CLASS { 
  TransactionBasicInformation               = 0,
  TransactionPropertiesInformation,
  TransactionEnlistmentInformation,
  TransactionSuperiorEnlistmentInformation
} TRANSACTION_INFORMATION_CLASS;
````


## -enum-fields




### -field TransactionBasicInformation

Information about a transaction manager object is stored in a <a href="..\wdm\ns-wdm-_transaction_basic_information.md">TRANSACTION_BASIC_INFORMATION</a> structure.


### -field TransactionPropertiesInformation

Information about a transaction manager object is stored in a <a href="..\wdm\ns-wdm-_transaction_properties_information.md">TRANSACTION_PROPERTIES_INFORMATION</a> structure.


### -field TransactionEnlistmentInformation

Information about a transaction manager object is stored in a <a href="..\wdm\ns-wdm-_transaction_enlistments_information.md">TRANSACTION_ENLISTMENTS_INFORMATION</a> structure.


### -field TransactionSuperiorEnlistmentInformation

Information about a transaction manager object is stored in a <b>TRANSACTION_SUPERIOR_ENLISTMENT_INFORMATION</b> structure.


## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationtransaction.md">ZwQueryInformationTransaction</a>



<a href="..\wdm\nf-wdm-zwsetinformationtransaction.md">ZwSetInformationTransaction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TRANSACTION_INFORMATION_CLASS enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

