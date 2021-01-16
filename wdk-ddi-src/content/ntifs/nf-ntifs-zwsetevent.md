---
UID: NF:ntifs.ZwSetEvent
title: ZwSetEvent function (ntifs.h)
description: The ZwSetEvent routine sets an event object to a Signaled state and attempts to satisfy as many waits as possible.
old-location: kernel\zwsetevent.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ZwSetEvent function"]
ms.keywords: NtSetEvent, ZwSetEvent, ZwSetEvent routine [Kernel-Mode Driver Architecture], k111_e01bbbbf-29f9-4c0a-89a2-84cf927aeb47.xml, kernel.zwsetevent, ntifs/NtSetEvent, ntifs/ZwSetEvent
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwSetEvent
 - ntifs/ZwSetEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwSetEvent
---

# ZwSetEvent function


## -description

The <b>ZwSetEvent</b> routine sets an event object to a Signaled state and attempts to satisfy as many waits as possible.

## -parameters

### -param EventHandle 

[in]
A handle to an event object.

### -param PreviousState 

[out, optional]
An optional pointer to a variable where the previous state of the event object is stored on output.

## -returns

<b>ZwSetEvent</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller did not have the required privileges to modify the event specified by the <i>EventHandle</i> parameter. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Resources required by this function could not be allocated. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The supplied <i>EventHandle</i> parameter was invalid. 

</td>
</tr>
</table>

## -remarks

<b>ZwSetEvent</b> sets an event object to a Signaled state and attempts to satisfy as many waits as possible.

<div class="alert"><b>Note</b>  If the call to the <b>ZwSetEvent</b> function occurs in user mode, you should use the name "<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-zwsetevent">NtSetEvent</a>" instead of "<b>ZwSetEvent</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatenotificationevent">IoCreateNotificationEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatesynchronizationevent">IoCreateSynchronizationEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent">KeClearEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keresetevent">KeResetEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetevent">KeSetEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-zwcreateevent">ZwCreateEvent</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-zwwaitforsingleobject">ZwWaitForSingleObject</a>

