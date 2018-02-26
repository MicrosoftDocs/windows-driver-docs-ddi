---
UID: NF:wdm.KeQueryDpcWatchdogInformation
title: KeQueryDpcWatchdogInformation function
author: windows-driver-content
description: The KeQueryDpcWatchdogInformation routine returns the deferred procedure call (DPC) watchdog timer values for the current processor.
old-location: kernel\kequerydpcwatchdoginformation.htm
old-project: kernel
ms.assetid: d776b815-815b-491d-b84b-5bf1944c9fac
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , D, I, K, KeQueryDpcWatchdogInformation, KeQueryDpcWatchdogInformation routine [Kernel-Mode Driver Architecture], Q, W, a, c, d, e, f, g, h, i, k105_0a2f37cc-0062-4315-b7f1-9bbe814d69b4.xml, kernel.kequerydpcwatchdoginformation, m, n, o, p, r, t, u, wdm/KeQueryDpcWatchdogInformation, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeQueryDpcWatchdogInformation
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryDpcWatchdogInformation function


## -description


The <b>KeQueryDpcWatchdogInformation</b> routine returns the deferred procedure call (DPC) watchdog timer values for the current processor.


## -syntax


````
NTSTATUS KeQueryDpcWatchdogInformation(
  _Out_ PKDPC_WATCHDOG_INFORMATION WatchdogInformation
);
````


## -parameters




### -param WatchdogInformation [out]

A pointer to a caller-supplied <a href="..\wdm\ns-wdm-_kdpc_watchdog_information.md">KDPC_WATCHDOG_INFORMATION</a> structure. The routine writes the current DPC watchdog timer values to this structure.


## -returns



<b>KeQueryDpcWatchdogInformation</b> returns an NTSTATUS value. Possible return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<b>KeQueryDpcWatchdogInformation</b> was called while a DPC was running on the current processor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The current processor was not running a DPC when <b>KeQueryDpcWatchdogInformation</b> was called.

</td>
</tr>
</table>
 




## -remarks



The <b>KeQueryDpcWatchdogInformation</b> routine can be called from a DPC routine or at an IRQL= DISPATCH_LEVEL to determine the amount of time that remains before a DPC time-out occurs. The operating system implements a DPC watchdog timer to detect when a single DPC routine runs for too long, or when a series of queued DPC routines runs back-to-back for too long. If DPC time-out errors are enabled, and if either a DPC routine exceeds the time limit for a single routine, or a series of DPC routines exceeds the aggregate time limit, a <a href="https://msdn.microsoft.com/CE9A4CBF-0016-42F7-A9EE-56DF6E61593A">DPC_WATCHDOG_VIOLATION</a> (0x133) bug check occurs.

<b>KeQueryDpcWatchdogInformation</b> must be called while a DPC is running or invoked at an IRQL= DISPATCH_LEVEL or higher on the current processor. Otherwise, the call fails and returns STATUS_UNSUCCESSFUL.

DPC routines should run only for brief periods, and should delegate as much processing as possible to worker threads. To avoid degrading system responsiveness, a typical DPC routine should run for no more than 100 microseconds each time it is called. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546551">Guidelines for Writing DPC Routines</a>.




## -see-also

<a href="..\wdm\ns-wdm-_kdpc_watchdog_information.md">KDPC_WATCHDOG_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryDpcWatchdogInformation routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

