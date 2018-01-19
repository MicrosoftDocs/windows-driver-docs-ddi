---
UID: NF:wdm.TmIsTransactionActive
title: TmIsTransactionActive function
author: windows-driver-content
description: The TmIsTransactionActive routine indicates whether a specified transaction is in its active state.
old-location: kernel\tmistransactionactive.htm
old-project: kernel
ms.assetid: 0c9bf43d-9342-4d60-86d2-7388a4a80160
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: TmIsTransactionActive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TmIsTransactionActive
req.alt-loc: NtosKrnl.exe,Ext-MS-Win-ntos-tm-l1-1-0.dll,tm.sys
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# TmIsTransactionActive function



## -description
The <b>TmIsTransactionActive</b> routine indicates whether a specified transaction is in its active state.



## -syntax

````
BOOLEAN TmIsTransactionActive(
  _In_ PKTRANSACTION Transaction
);
````


## -parameters

### -param Transaction [in]

A pointer to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. To obtain this pointer, your component must call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a> or <a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a> provided.


## -returns
<b>TmIsTransactionActive</b> returns <b>TRUE</b> if the specified transaction is in its active state. Otherwise, the routine returns <b>FALSE</b>.


## -remarks
When a transaction is created, it enters its active state and remains in that state until the <a href="https://msdn.microsoft.com/4885476e-ce68-4674-b8a5-8a317f33cd5b">pre-prepare/prepare/commit sequence</a> begins. 

For more information about <b>TmIsTransactionActive</b>, and for information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatetransaction.md">ZwCreateTransaction</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopentransaction.md">ZwOpenTransaction</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmIsTransactionActive routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

