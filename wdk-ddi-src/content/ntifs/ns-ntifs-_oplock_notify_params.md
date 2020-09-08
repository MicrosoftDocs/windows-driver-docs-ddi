---
UID: NS:ntifs._OPLOCK_NOTIFY_PARAMS
title: _OPLOCK_NOTIFY_PARAMS (ntifs.h)
description: The OPLOCK_NOTIFY_PARAMS structure is passed as a parameter to a NotifyRoutine callback when such a callback is provided to FsRtlCheckOplockEx2.
old-location: ifsk\OPLOCK_NOTIFY_PARAMS_.htm
tech.root: ifsk
ms.assetid: d47100ad-cef6-4941-86dd-73f7eff97061
ms.date: 03/24/2020
ms.keywords: "*POPLOCK_NOTIFY_PARAMS, OPLOCK_NOTIFY_PARAMS, OPLOCK_NOTIFY_PARAMS structure [File System Drivers], FsRtlCheckOplockEx2"
ms.topic: struct
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 2004
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: OPLOCK_NOTIFY_PARAMS, *POPLOCK_NOTIFY_PARAMS
f1_keywords:
 - _OPLOCK_NOTIFY_PARAMS
 - ntifs/_OPLOCK_NOTIFY_PARAMS
 - POPLOCK_NOTIFY_PARAMS
 - ntifs/POPLOCK_NOTIFY_PARAMS
 - OPLOCK_NOTIFY_PARAMS
 - ntifs/OPLOCK_NOTIFY_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - OPLOCK_NOTIFY_PARAMS
---

# _OPLOCK_NOTIFY_PARAMS structure


## -description

The OPLOCK_NOTIFY_PARAMS structure is passed as a parameter to a *NotifyRoutine* callback when such a callback is provided to [**FsRtlCheckOplockEx2**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckoplockex2.md).

## -struct-fields

### -field NotifyReason

An [OPLOCK_NOTIFY_REASON](ne-ntifs-_oplock_notify_reason.md) enumeration value that specifies the reason for the notification callback.

### -field NotifyContext

Set to be the same value as **FsRtlCheckOplockEx2**'s *NotifyContext* parameter.

### -field Irp

Set to be the same value as **FsRtlCheckOplockEx2**'s *Irp* parameter.

### -field Status

The NT status code returned from the *NotifyRoutine* callback. The interpretation of the status code depends on the value of *NotifyReason*.

## -remarks

## -see-also

[**FsRtlCheckOplockEx2**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckoplockex2.md)

[OPLOCK_NOTIFY_REASON](ne-ntifs-_oplock_notify_reason.md)

