---
UID: NF:ntifs.PsGetProcessExitTime
title: PsGetProcessExitTime function (ntifs.h)
description: The PsGetProcessExitTime routine returns the exit time for the current process.
old-location: ifsk\psgetprocessexittime.htm
tech.root: ifsk
ms.assetid: 2d98e2f5-0dc4-4490-a039-eb57f0e5fa87
ms.date: 04/16/2018
keywords: ["PsGetProcessExitTime function"]
ms.keywords: PsGetProcessExitTime, PsGetProcessExitTime routine [Installable File System Drivers], ifsk.psgetprocessexittime, ntifs/PsGetProcessExitTime, psref_a3867d14-4a6b-4560-a580-cdc00075b185.xml
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PsGetProcessExitTime
 - ntifs/PsGetProcessExitTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsGetProcessExitTime
---

# PsGetProcessExitTime function


## -description

The <b>PsGetProcessExitTime</b> routine returns the exit time for the current process.

## -returns

<b>PsGetProcessExitTime</b> returns the exit time for the current process, in system time format.

## -remarks

System time is a count of 100-nanosecond intervals since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. To adjust this value for the local time zone, use <b>ExSystemTimeToLocalTime</b>.

For more information about converting time values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Data Conversions</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerysystemtime">KeQuerySystemTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psisthreadterminating">PsIsThreadTerminating</a>

