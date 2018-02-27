---
UID: NE:wdm._KTMOBJECT_TYPE
title: "_KTMOBJECT_TYPE"
author: windows-driver-content
description: The KTMOBJECT_TYPE enumeration identifies the types of objects that KTM supports.
old-location: kernel\ktmobject_type.htm
old-project: kernel
ms.assetid: 0ace1cdf-0a15-48bb-9444-c947239e453e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PKTMOBJECT_TYPE, KTMOBJECT_ENLISTMENT, KTMOBJECT_INVALID, KTMOBJECT_RESOURCE_MANAGER, KTMOBJECT_TRANSACTION, KTMOBJECT_TRANSACTION_MANAGER, KTMOBJECT_TYPE, KTMOBJECT_TYPE enumeration [Kernel-Mode Driver Architecture], PKTMOBJECT_TYPE, PKTMOBJECT_TYPE enumeration pointer [Kernel-Mode Driver Architecture], _KTMOBJECT_TYPE, kernel.ktmobject_type, ktm_ref_1f145c7b-775d-4d0f-b5cd-1e09f5c5b438.xml, wdm/KTMOBJECT_ENLISTMENT, wdm/KTMOBJECT_INVALID, wdm/KTMOBJECT_RESOURCE_MANAGER, wdm/KTMOBJECT_TRANSACTION, wdm/KTMOBJECT_TRANSACTION_MANAGER, wdm/KTMOBJECT_TYPE, wdm/PKTMOBJECT_TYPE"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	KTMOBJECT_TYPE
product: Windows
targetos: Windows
req.typenames: KTMOBJECT_TYPE, *PKTMOBJECT_TYPE
req.product: Windows 10 or later.
---

# _KTMOBJECT_TYPE enumeration


## -description


The <b>KTMOBJECT_TYPE</b> enumeration identifies the types of objects that KTM supports.


## -syntax


````
typedef enum _KTMOBJECT_TYPE { 
  KTMOBJECT_TRANSACTION          = 0,
  KTMOBJECT_TRANSACTION_MANAGER  = 1,
  KTMOBJECT_RESOURCE_MANAGER     = 2,
  KTMOBJECT_ENLISTMENT           = 3,
  KTMOBJECT_INVALID              = 4
} KTMOBJECT_TYPE, *PKTMOBJECT_TYPE;
````


## -enum-fields




### -field KTMOBJECT_TRANSACTION

KTM transaction objects.


### -field KTMOBJECT_TRANSACTION_MANAGER

KTM transaction manager objects.


### -field KTMOBJECT_RESOURCE_MANAGER

KTM resource manager objects.


### -field KTMOBJECT_ENLISTMENT

KTM enlistment objects.


### -field KTMOBJECT_INVALID

Invalid object type.


## -remarks



The <b>KTMOBJECT_TYPE</b> enumeration is used with the <a href="..\wdm\nf-wdm-zwenumeratetransactionobject.md">ZwEnumerateTransactionObject</a> routine.

For more information about KTM objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554272">KTM Objects</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwenumeratetransactionobject.md">ZwEnumerateTransactionObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KTMOBJECT_TYPE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

