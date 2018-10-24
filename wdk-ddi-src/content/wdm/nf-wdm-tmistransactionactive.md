---
UID: NF:wdm.TmIsTransactionActive
title: TmIsTransactionActive function
author: windows-driver-content
description: The TmIsTransactionActive routine indicates whether a specified transaction is in its active state.
old-location: kernel\tmistransactionactive.htm
tech.root: kernel
ms.assetid: 0c9bf43d-9342-4d60-86d2-7388a4a80160
ms.date: 04/30/2018
ms.keywords: TmIsTransactionActive, TmIsTransactionActive routine [Kernel-Mode Driver Architecture], kernel.tmistransactionactive, ktm_ref_f2dfbc14-24c0-494b-bf54-506c9d2c1af4.xml, wdm/TmIsTransactionActive
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
-	TmIsTransactionActive
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmIsTransactionActive function


## -description


The <b>TmIsTransactionActive</b> routine indicates whether a specified transaction is in its active state.


## -parameters




### -param Transaction [in]

A pointer to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. To obtain this pointer, your component must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a> provided.


## -returns



<b>TmIsTransactionActive</b> returns <b>TRUE</b> if the specified transaction is in its active state. Otherwise, the routine returns <b>FALSE</b>.




## -remarks



When a transaction is created, it enters its active state and remains in that state until the <a href="https://msdn.microsoft.com/4885476e-ce68-4674-b8a5-8a317f33cd5b">pre-prepare/prepare/commit sequence</a> begins. 

For more information about <b>TmIsTransactionActive</b>, and for information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a>
 

 

