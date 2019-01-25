---
UID: NF:wdm.TmRequestOutcomeEnlistment
title: TmRequestOutcomeEnlistment function (wdm.h)
description: The TmRequestOutcomeEnlistment routine asks KTM to try to provide an immediate outcome (commit or rollback) for the transaction that is associated with a specified enlistment.
old-location: kernel\tmrequestoutcomeenlistment.htm
tech.root: kernel
ms.assetid: 1e58be94-7a10-4708-a658-9de28e26a465
ms.date: 04/30/2018
ms.keywords: TmRequestOutcomeEnlistment, TmRequestOutcomeEnlistment routine [Kernel-Mode Driver Architecture], kernel.tmrequestoutcomeenlistment, ktm_ref_9be6bea7-eae4-4621-8155-f8a06285bb97.xml, wdm/TmRequestOutcomeEnlistment
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
req.irql: PASSIVE_LEVEL
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
-	TmRequestOutcomeEnlistment
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmRequestOutcomeEnlistment function


## -description


The <b>TmRequestOutcomeEnlistment</b> routine asks KTM to try to provide an immediate outcome (commit or rollback) for the transaction that is associated with a specified enlistment.


## -parameters




### -param Enlistment [in]

A pointer to an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>. Your component can receive this pointer as input to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff564669">TmCreateEnlistment</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567008">ZwOpenEnlistment</a> provided.


### -param TmVirtualClock [in]

A pointer to a <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>TmRequestOutcomeEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return the following value: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The specified enlistment is a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior enlistment</a>.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>TmRequestOutcomeEnlistment</b> routine asks KTM to try to provide an immediate outcome (result) for the transaction. A resource manager can call <b>TmRequestOutcomeEnlistment</b> after it has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff564687">TmPrepareComplete</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567037">ZwPrepareComplete</a>, if it later discovers that it cannot wait for an outcome because, for example, a surprise-removal of the disk has occurred. KTM might be able to force a rollback if all resource managers have not finished their prepare operations.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of Zw<i>Xxx</i> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.

For more information about <b>TmCreateEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564669">TmCreateEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564687">TmPrepareComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567008">ZwOpenEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567037">ZwPrepareComplete</a>
 

 

