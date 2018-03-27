---
UID: NF:ntifs.PsIsDiskCountersEnabled
title: PsIsDiskCountersEnabled function
author: windows-driver-content
description: The enabled state of the per process disk I/O counters is returned by the PsIsDiskCountersEnabled routine.
old-location: ifsk\psisdiskcountersenabled.htm
old-project: ifsk
ms.assetid: E4626CF9-5E76-4C48-9B38-274178E41E30
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PsIsDiskCountersEnabled, PsIsDiskCountersEnabled routine [Installable File System Drivers], ifsk.psisdiskcountersenabled, ntifs/PsIsDiskCountersEnabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsIsDiskCountersEnabled
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsIsDiskCountersEnabled function


## -description


The enabled state of the per process disk I/O counters is returned by the <b>PsIsDiskCountersEnabled</b> routine.


## -parameters






## -returns



If TRUE, the disk




## -remarks



A file system driver uses the <b>PsIsDiskCountersEnabled</b> routine to query the system enabled  state of the disk I/O  counters. A file system driver will use this routine prior to accounting for process disk I/O using <a href="https://msdn.microsoft.com/library/windows/hardware/hh971609">PsUpdateDiskCounters</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh971609">PsUpdateDiskCounters</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsIsDiskCountersEnabled routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

