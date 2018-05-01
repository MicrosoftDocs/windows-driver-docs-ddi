---
UID: NE:wdm._KTMOBJECT_TYPE
title: "_KTMOBJECT_TYPE"
author: windows-driver-content
description: The KTMOBJECT_TYPE enumeration identifies the types of objects that KTM supports.
old-location: kernel\ktmobject_type.htm
old-project: kernel
ms.assetid: 0ace1cdf-0a15-48bb-9444-c947239e453e
ms.author: windowsdriverdev
ms.date: 4/5/2018
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	KTMOBJECT_TYPE
product: Windows
targetos: Windows
req.typenames: KTMOBJECT_TYPE, *PKTMOBJECT_TYPE
---

# _KTMOBJECT_TYPE enumeration


## -description


The <b>KTMOBJECT_TYPE</b> enumeration identifies the types of objects that KTM supports.


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



The <b>KTMOBJECT_TYPE</b> enumeration is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566450">ZwEnumerateTransactionObject</a> routine.

For more information about KTM objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554272">KTM Objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566450">ZwEnumerateTransactionObject</a>
 

 

