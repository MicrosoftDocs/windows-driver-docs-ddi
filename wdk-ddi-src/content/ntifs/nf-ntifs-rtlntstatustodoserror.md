---
UID: NF:ntifs.RtlNtStatusToDosError
title: RtlNtStatusToDosError function (ntifs.h)
description: The RtlNtStatusToDosError routine converts the specified NTSTATUS code to its equivalent system error code.
old-location: ifsk\rtlntstatustodoserror.htm
tech.root: ifsk
ms.assetid: 9ba6f693-b0b7-4176-b951-7bb259bec391
ms.date: 04/16/2018
keywords: ["RtlNtStatusToDosError function"]
ms.keywords: RtlNtStatusToDosError, RtlNtStatusToDosError routine [Installable File System Drivers], ifsk.rtlntstatustodoserror, ntifs/RtlNtStatusToDosError, rtlref_8afdfe24-1071-4bab-b935-b1b91eb52766.xml
f1_keywords:
 - "ntifs/RtlNtStatusToDosError"
 - "RtlNtStatusToDosError"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The RtlNtStatusToDosError routine is available on Microsoft Windows 2000 and later versions of Windows.
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
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlNtStatusToDosError
targetos: Windows
req.typenames: 
---

# RtlNtStatusToDosError function


## -description


The <b>RtlNtStatusToDosError</b> routine converts the specified NTSTATUS code to its equivalent system error code. 


## -parameters




### -param Status 
[in]
The NTSTATUS code to be converted.


## -returns



<b>RtlNtStatusToDosError</b> returns the corresponding system error code. Error codes are defined in <i>Winerror.h</i>.

<b>RtlNtStatusToDosError</b> returns ERROR_MR_MID_NOT_FOUND when the specified NTSTATUS code does not have a corresponding system error code. For more information about system error codes, see  <a href="https://docs.microsoft.com/windows/desktop/Debug/system-error-codes">System Error Codes</a>. 




## -remarks



There is no function that provides the inverse functionality of <b>RtlNtStatusToDosError</b>, converting a system error code to its corresponding NTSTATUS code. 



