---
UID: NF:wdm.TmDereferenceEnlistmentKey
title: TmDereferenceEnlistmentKey function
author: windows-driver-content
description: The TmDereferenceEnlistmentKey routine decrements the reference count for the key of a specified enlistment object.
old-location: kernel\tmdereferenceenlistmentkey.htm
old-project: kernel
ms.assetid: e03b5f4d-58d5-43d5-a0c3-8a3cc83bd38a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: TmDereferenceEnlistmentKey
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
req.alt-api: TmDereferenceEnlistmentKey
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
req.irql: <= DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# TmDereferenceEnlistmentKey function



## -description
The <b>TmDereferenceEnlistmentKey</b> routine decrements the reference count for the key of a specified <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>.



## -syntax

````
NTSTATUS TmDereferenceEnlistmentKey(
  _In_      PKENLISTMENT Enlistment,
  _Out_opt_ PBOOLEAN     LastReference
);
````


## -parameters

### -param Enlistment [in]

A pointer to an enlistment object. Your component can receive this pointer as input to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>, <a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>, or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a> provided.


### -param LastReference [out, optional]

A pointer to a BOOLEAN-typed variable. This variable receives <b>TRUE</b> if the reference count is zero after <b>TmDereferenceEnlistmentKey</b> decrements it. Otherwise, the variable receives <b>FALSE</b>.


## -returns
<b>TmDereferenceEnlistmentKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>The reference count of the specified enlistment object is zero and cannot be decremented.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
The <a href="..\wdm\nf-wdm-tmreferenceenlistmentkey.md">TmReferenceEnlistmentKey</a> routine increments the reference count for an enlistment object's key, and the <b>TmDereferenceEnlistmentKey</b> routine decrements the count.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-tmreferenceenlistmentkey.md">TmReferenceEnlistmentKey</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmDereferenceEnlistmentKey routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

