---
UID: NS:wdm._TRANSACTION_PROPERTIES_INFORMATION
title: "_TRANSACTION_PROPERTIES_INFORMATION"
description: The TRANSACTION_PROPERTIES_INFORMATION structure contains a transaction object's properties.
old-location: kernel\transaction_properties_information.htm
tech.root: kernel
ms.assetid: 76b0f102-0d09-4b16-b8e1-727a3a6e48c9
ms.date: 04/30/2018
ms.keywords: "*PTRANSACTION_PROPERTIES_INFORMATION, PTRANSACTION_PROPERTIES_INFORMATION, PTRANSACTION_PROPERTIES_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTION_PROPERTIES_INFORMATION, TRANSACTION_PROPERTIES_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTION_PROPERTIES_INFORMATION, kernel.transaction_properties_information, ktm_ref_bc17351c-f0ea-457e-968c-19785c0afd8d.xml, wdm/PTRANSACTION_PROPERTIES_INFORMATION, wdm/TRANSACTION_PROPERTIES_INFORMATION"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	TRANSACTION_PROPERTIES_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: TRANSACTION_PROPERTIES_INFORMATION, *PTRANSACTION_PROPERTIES_INFORMATION
---

# _TRANSACTION_PROPERTIES_INFORMATION structure


## -description


The <b>TRANSACTION_PROPERTIES_INFORMATION</b> structure contains a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object's</a> properties.


## -struct-fields




### -field IsolationLevel

Reserved for future use.


### -field IsolationFlags

Reserved for future use.


### -field Timeout

A time-out value. If the transaction has not been committed by the time specified by this parameter, KTM rolls back the transaction. The time-out value is expressed in system time units (100-nanosecond intervals), and can specify either an absolute time or a relative time. If the value of the <b>Timeout</b> member is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. Set this member to zero if no time-out is required. If <b>Timeout</b> is zero, the transaction never times out.


### -field Outcome

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff564835">TRANSACTION_OUTCOME</a>-typed value that identifies the transaction's outcome (result). You can obtain this value by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567057">ZwQueryInformationTransaction</a>, but you cannot set the value with <a href="https://msdn.microsoft.com/library/windows/hardware/ff567104">ZwSetInformationTransaction</a>.


### -field DescriptionLength

The size, in bytes, of the buffer that contains the <b>Description</b> member's array.


### -field Description

A caller-allocated array of characters that contains or receives the transaction's description string. The <a href="https://msdn.microsoft.com/75d4758b-dfba-431b-9bfa-9dcb98c2a7cc">TPS client</a> can specify this string when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a>. The client can retrieve the string by calling by calling <b>ZwQueryInformationTransaction</b>, and it can modify the string by calling <b>ZwSetInformationTransaction</b>.


## -remarks



The <b>TRANSACTION_PROPERTIES_INFORMATION</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567057">ZwQueryInformationTransaction</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567104">ZwSetInformationTransaction</a> routines.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564800">TRANSACTION_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564835">TRANSACTION_OUTCOME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567057">ZwQueryInformationTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567104">ZwSetInformationTransaction</a>
 

 

