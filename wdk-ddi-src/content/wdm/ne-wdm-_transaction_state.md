---
UID: NE:wdm._TRANSACTION_STATE
title: "_TRANSACTION_STATE"
author: windows-driver-content
description: The TRANSACTION_STATE enumeration defines the states that KTM can assign to a transaction.
old-location: kernel\transaction_state.htm
old-project: kernel
ms.assetid: b97bedc5-6393-49bd-b803-e70e3a3d49df
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: TRANSACTION_STATE, TRANSACTION_STATE enumeration [Kernel-Mode Driver Architecture], TransactionStateCommittedNotify, TransactionStateIndoubt, TransactionStateNormal, _TRANSACTION_STATE, kernel.transaction_state, ktm_ref_051131c5-e3a5-430e-afca-053fcb68f746.xml, wdm/TRANSACTION_STATE, wdm/TransactionStateCommittedNotify, wdm/TransactionStateIndoubt, wdm/TransactionStateNormal
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	TRANSACTION_STATE
product: Windows
targetos: Windows
req.typenames: TRANSACTION_STATE
req.product: Windows 10 or later.
---

# _TRANSACTION_STATE enumeration


## -description


The <b>TRANSACTION_STATE</b> enumeration defines the states that KTM can assign to a transaction.


## -syntax


````
typedef enum _TRANSACTION_STATE { 
  TransactionStateNormal           = 1,
  TransactionStateIndoubt          = 2,
  TransactionStateCommittedNotify  = 3
} TRANSACTION_STATE;
````


## -enum-fields




### -field TransactionStateNormal

The transaction's state is neither in doubt nor committed.


### -field TransactionStateIndoubt

The transaction's state is in doubt (that is, KTM cannot determine whether the transaction should be committed or rolled back). A transaction that has been prepared enters the "in doubt" state if its <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> becomes unavailable.


### -field TransactionStateCommittedNotify

The transaction has been committed. Commit notifications might (or might not) have been delivered to all enlistments.


## -remarks



The <b>TRANSACTION_STATE</b> enumeration is used in the <a href="..\wdm\ns-wdm-_transaction_basic_information.md">TRANSACTION_BASIC_INFORMATION</a> structure.




## -see-also

<a href="..\wdm\ns-wdm-_transaction_basic_information.md">TRANSACTION_BASIC_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TRANSACTION_STATE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

