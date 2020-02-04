---
UID: NF:ntifs.FsRtlIsNtstatusExpected
title: FsRtlIsNtstatusExpected function (ntifs.h)
description: The FsRtlIsNtstatusExpected routine determines whether the specified exception is handled by the exception filter.
old-location: ifsk\fsrtlisntstatusexpected.htm
tech.root: ifsk
ms.assetid: 7d495d67-fe43-43d5-8a35-50c070b78b8d
ms.date: 04/16/2018
ms.keywords: FsRtlIsNtstatusExpected, FsRtlIsNtstatusExpected routine [Installable File System Drivers], fsrtlref_c480df4e-1601-4df7-809f-b1dec9549412.xml, ifsk.fsrtlisntstatusexpected, ntifs/FsRtlIsNtstatusExpected
f1_keywords:
 - "ntifs/FsRtlIsNtstatusExpected"
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlIsNtstatusExpected
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlIsNtstatusExpected function


## -description


The <b>FsRtlIsNtstatusExpected</b> routine determines whether the specified exception is handled by the exception filter.


## -parameters




### -param Exception [in]

Status value of the exception.


## -returns



<b>FsRtlIsNtstatusExpected</b> returns <b>TRUE</b> if the status value indicates a nonfatal system error status, <b>FALSE</b> otherwise.




## -remarks



File systems use <b>FsRtlIsNtstatusExpected</b> to determine whether to attempt to handle an exception. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlnormalizentstatus">FsRtlNormalizeNtstatus</a>
 

 

