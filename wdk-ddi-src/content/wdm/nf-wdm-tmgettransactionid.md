---
UID: NF:wdm.TmGetTransactionId
title: TmGetTransactionId function
description: The TmGetTransactionId routine retrieves a transaction object's unit of work (UOW) identifier.
old-location: kernel\tmgettransactionid.htm
tech.root: kernel
ms.assetid: 8ff4dd86-d828-4e1d-bde5-ab312187a8d7
ms.date: 04/30/2018
ms.keywords: TmGetTransactionId, TmGetTransactionId routine [Kernel-Mode Driver Architecture], kernel.tmgettransactionid, ktm_ref_cbb12580-5399-4d81-ab6c-9d0235208681.xml, wdm/TmGetTransactionId
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
api_name:
-	TmGetTransactionId
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmGetTransactionId function


## -description


The <b>TmGetTransactionId</b> routine retrieves a transaction object's <a href="https://msdn.microsoft.com/927a417b-35f5-49b8-85f3-7e6b1f5c0225">unit of work (UOW) identifier</a>.


## -parameters




### -param Transaction [in]

A pointer to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. To obtain this pointer, your component must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a> provided.


### -param TransactionId [out]

A pointer to a location that receives the transaction object's UOW identifier.


## -returns



None




## -remarks



For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567057">ZwQueryInformationTransaction</a>
 

 

