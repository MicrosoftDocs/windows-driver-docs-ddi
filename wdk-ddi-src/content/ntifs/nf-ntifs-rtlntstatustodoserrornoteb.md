---
UID: NF:ntifs.RtlNtStatusToDosErrorNoTeb
title: RtlNtStatusToDosErrorNoTeb function (ntifs.h)
description: "Microsoft reserves the RtlNtStatusToDosErrorNoTeb function for internal use only. Don't use this function in your code."
old-location: ifsk\rtlntstatustodoserrornoteb.htm
tech.root: ifsk
ms.date: 11/04/2022
ms.custom: content-health
keywords: ["RtlNtStatusToDosErrorNoTeb function"]
ms.keywords: RtlNtStatusToDosError, RtlNtStatusToDosError routine [Installable File System Drivers], RtlNtStatusToDosErrorNoTeb, ifsk.rtlntstatustodoserrornoteb, ntifs/RtlNtStatusToDosError, rtlref_161ea08b-d596-4a3c-ab9b-b66f757e4415.xml
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
 - RtlNtStatusToDosErrorNoTeb
 - ntifs/RtlNtStatusToDosErrorNoTeb
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlNtStatusToDosErrorNoTeb
---

# RtlNtStatusToDosErrorNoTeb function

## -description

The **RtlNtStatusToDosErrorNoTeb**  routine converts the specified NTSTATUS code to its equivalent system error code. Reserved for system use.

## -parameters

### -param Status [in]

The NTSTATUS code to be converted.

## -returns

**RtlNtStatusToDosErrorNoTeb** returns the corresponding system error code. Error codes are defined in *Winerror.h*. For more information about system error codes, see [System Error Codes](/windows/desktop/Debug/system-error-codes).

## -remarks

There is no function that provides the inverse functionality of **RtlNtStatusToDosErrorNoTeb**, converting a system error code to its corresponding NTSTATUS code.

