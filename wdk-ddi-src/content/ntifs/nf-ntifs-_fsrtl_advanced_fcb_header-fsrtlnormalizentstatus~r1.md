---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNormalizeNtstatus~r1
title: FsRtlNormalizeNtstatus function (ntifs.h)
description: The FsRtlNormalizeNtstatus routine translates an arbitrary exception into a status value that is handled by the exception filter.
old-location: ifsk\fsrtlnormalizentstatus.htm
tech.root: ifsk
ms.assetid: ed085787-6731-42b5-9e19-adedbad11a9c
ms.date: 03/29/2018
ms.keywords: FsRtlNormalizeNtstatus, FsRtlNormalizeNtstatus routine [Installable File System Drivers], fsrtlref_f31a9a77-7deb-4919-bfae-874958b15c7f.xml, ifsk.fsrtlnormalizentstatus, ntifs/FsRtlNormalizeNtstatus
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlNormalizeNtstatus"
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
- FsRtlNormalizeNtstatus
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlNormalizeNtstatus function


## -description


The <b>FsRtlNormalizeNtstatus</b> routine translates an arbitrary exception into a status value that is handled by the exception filter.


## -parameters




### -param Exception [in]

Status value of the exception.


### -param GenericException [in]

Generic status value to return if <i>Exception</i> is not within the set of exceptions handled by the filter.


## -returns



<b>FsRtlNormalizeNtstatus</b> returns <i>Exception</i> if the status value is handled by the exception filter, <i>GenericException</i> otherwise.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisntstatusexpected">FsRtlIsNtstatusExpected</a>
 

 

