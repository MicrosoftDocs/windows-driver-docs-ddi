---
UID: NF:ntifs.RtlNtStatusToDosError
title: RtlNtStatusToDosError function (ntifs.h)
description: The RtlNtStatusToDosError routine converts the specified NTSTATUS code to its equivalent system error code.
old-location: ifsk\rtlntstatustodoserror.htm
tech.root: ifsk
ms.date: 11/04/2022
ms.custom: content-health
keywords: ["RtlNtStatusToDosError function"]
ms.keywords: RtlNtStatusToDosError, RtlNtStatusToDosError routine [Installable File System Drivers], ifsk.rtlntstatustodoserror, ntifs/RtlNtStatusToDosError, rtlref_8afdfe24-1071-4bab-b935-b1b91eb52766.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlNtStatusToDosError
 - ntifs/RtlNtStatusToDosError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlNtStatusToDosError
---

# RtlNtStatusToDosError function

## -description

The **RtlNtStatusToDosError** routine converts the specified NTSTATUS code to its equivalent system error code.

## -parameters

### -param Status [in]

The NTSTATUS code to be converted.

## -returns

**RtlNtStatusToDosError** returns the corresponding system error code. Error codes are defined in *Winerror.h*.

**RtlNtStatusToDosError** returns ERROR_MR_MID_NOT_FOUND when the specified NTSTATUS code does not have a corresponding system error code. For more information about system error codes, see [System Error Codes](/windows/desktop/Debug/system-error-codes).

## -remarks

There is no function that provides the inverse functionality of **RtlNtStatusToDosError**, converting a system error code to its corresponding NTSTATUS code.
