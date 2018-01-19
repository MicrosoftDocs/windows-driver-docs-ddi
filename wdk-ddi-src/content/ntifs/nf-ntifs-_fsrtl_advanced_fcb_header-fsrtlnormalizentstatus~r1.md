---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNormalizeNtstatus~r1
title: FsRtlNormalizeNtstatus function
author: windows-driver-content
description: The FsRtlNormalizeNtstatus routine translates an arbitrary exception into a status value that is handled by the exception filter.
old-location: ifsk\fsrtlnormalizentstatus.htm
old-project: ifsk
ms.assetid: ed085787-6731-42b5-9e19-adedbad11a9c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlNormalizeNtstatus
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
req.alt-api: FsRtlNormalizeNtstatus
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# FsRtlNormalizeNtstatus function



## -description
The <b>FsRtlNormalizeNtstatus</b> routine translates an arbitrary exception into a status value that is handled by the exception filter.



## -syntax

````
NTSTATUS FsRtlNormalizeNtstatus(
  _In_ NTSTATUS Exception,
  _In_ NTSTATUS GenericException
);
````


## -parameters

### -param Exception [in]

Status value of the exception.


### -param GenericException [in]

Generic status value to return if <i>Exception</i> is not within the set of exceptions handled by the filter.


## -returns
<b>FsRtlNormalizeNtstatus</b> returns <i>Exception</i> if the status value is handled by the exception filter, <i>GenericException</i> otherwise.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisntstatusexpected.md">FsRtlIsNtstatusExpected</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlNormalizeNtstatus routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

