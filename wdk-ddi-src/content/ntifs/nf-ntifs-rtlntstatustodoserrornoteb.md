---
UID: NF:ntifs.RtlNtStatusToDosErrorNoTeb
title: RtlNtStatusToDosErrorNoTeb function (ntifs.h)
description: Reserved for system use.
old-location: ifsk\rtlntstatustodoserrornoteb.htm
tech.root: ifsk
ms.assetid: be22fb7f-408a-44ee-ae83-0f1dadcec87f
ms.date: 04/16/2018
ms.keywords: RtlNtStatusToDosError, RtlNtStatusToDosError routine [Installable File System Drivers], RtlNtStatusToDosErrorNoTeb, ifsk.rtlntstatustodoserrornoteb, ntifs/RtlNtStatusToDosError, rtlref_161ea08b-d596-4a3c-ab9b-b66f757e4415.xml
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The RtlNtStatusToDosErrorNoTeb routine is available on Microsoft Windows 2000 and later versions of Windows.
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlNtStatusToDosError
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlNtStatusToDosErrorNoTeb function


## -description


The <b>RtlNtStatusToDosErrorNoTeb</b>  routine converts the specified NTSTATUS code to its equivalent system error code. Reserved for system use.


## -parameters




### -param Status [in]

The NTSTATUS code to be converted.


## -returns



<b>RtlNtStatusToDosErrorNoTeb</b> returns the corresponding system error code. Error codes are defined in <i>Winerror.h</i>.




## -remarks



There is no function that provides the inverse functionality of <b>RtlNtStatusToDosErrorNoTeb</b>, converting a system error code to its corresponding NTSTATUS code. 



