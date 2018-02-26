---
UID: NF:ntifs.PsGetProcessExitTime
title: PsGetProcessExitTime function
author: windows-driver-content
description: The PsGetProcessExitTime routine returns the exit time for the current process.
old-location: ifsk\psgetprocessexittime.htm
old-project: ifsk
ms.assetid: 2d98e2f5-0dc4-4490-a039-eb57f0e5fa87
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , E, G, P, PsGetProcessExitTime, PsGetProcessExitTime routine [Installable File System Drivers], T, c, e, i, ifsk.psgetprocessexittime, m, ntifs/PsGetProcessExitTime, o, psref_a3867d14-4a6b-4560-a580-cdc00075b185.xml, r, s, t, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsGetProcessExitTime
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsGetProcessExitTime function


## -description


The <b>PsGetProcessExitTime</b> routine returns the exit time for the current process.


## -syntax


````
LARGE_INTEGER PsGetProcessExitTime(
   VOID 
);
````


## -parameters








## -returns



<b>PsGetProcessExitTime</b> returns the exit time for the current process, in system time format. 




## -remarks



System time is a count of 100-nanosecond intervals since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. To adjust this value for the local time zone, use <b>ExSystemTimeToLocalTime</b>.

For more information about converting time values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542994">Data Conversions</a>. 




## -see-also

<a href="..\wdm\nf-wdm-exsystemtimetolocaltime.md">ExSystemTimeToLocalTime</a>



<a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a>



<a href="..\ntifs\nf-ntifs-psisthreadterminating.md">PsIsThreadTerminating</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsGetProcessExitTime routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

