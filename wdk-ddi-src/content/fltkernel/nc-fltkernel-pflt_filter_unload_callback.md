---
UID: NC:fltkernel.PFLT_FILTER_UNLOAD_CALLBACK
title: PFLT_FILTER_UNLOAD_CALLBACK (fltkernel.h)
description: A minifilter driver can register a routine of type PFLT_FILTER_UNLOAD_CALLBACK as the minifilter driver's FilterUnloadCallback routine.
old-location: ifsk\pflt_filter_unload_callback.htm
tech.root: ifsk
ms.assetid: 746f13f5-c92d-4dae-8fd7-4c9fdfa9e044
ms.date: 05/09/2019
keywords: ["PFLT_FILTER_UNLOAD_CALLBACK callback function"]
ms.keywords: FilterUnloadCallback, FilterUnloadCallback routine [Installable File System Drivers], FltCallbacks_e28b1a16-b974-493a-8ab5-7b6004d66268.xml, PFLT_FILTER_UNLOAD_CALLBACK, fltkernel/FilterUnloadCallback, ifsk.pflt_filter_unload_callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFLT_FILTER_UNLOAD_CALLBACK
 - fltkernel/PFLT_FILTER_UNLOAD_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fltkernel.h
api_name:
 - FilterUnloadCallback
---

# PFLT_FILTER_UNLOAD_CALLBACK callback function


## -description

A minifilter driver can register a routine of type PFLT_FILTER_UNLOAD_CALLBACK as the minifilter driver's *FilterUnloadCallback* routine.

## -parameters

### -param Flags

Bitmask of flags describing the unload request. This parameter can be **NULL** or the following:

| Flag  | Meaning |
| ----- | ------  |
| FLTFL_FILTER_UNLOAD_MANDATORY | The filter manager sets this flag to indicate that the unload operation is mandatory. |

## -returns

This callback routine returns STATUS_SUCCESS or an NTSTATUS value such as the following:

| Return Code | Description |
| ----------- | ----------- |
| STATUS_FLT_DO_NOT_DETACH | If the unload operation is not mandatory, returning this status value prevents the minifilter driver from being unloaded. This is an error code. |

## -remarks

When a minifilter driver registers itself by calling [FltRegisterFilter](nf-fltkernel-fltregisterfilter.md), it can register a *FilterUnloadCallback* routine. To register this callback routine, the minifilter driver stores the address of a routine of type PFLT_FILTER_UNLOAD_CALLBACK in the **FilterUnloadCallback** field of the [FLT_REGISTRATION](ns-fltkernel-_flt_registration.md) structure that the minifilter driver passes as a parameter to **FltRegisterFilter**.

Minifilter drivers are not required to register a *FilterUnloadCallback* routine. However, registering an unload routine is strongly recommended. If a minifilter driver does not register a *FilterUnloadCallback* routine, it cannot be unloaded.

When a minifilter driver does register a *FilterUnloadCallback* routine:

* The filter manager calls the *FilterUnloadCallback* routine to notify the minifilter driver that the filter manager is about to unload the minifilter driver.

* If the unload operation is not mandatory, and the *FilterUnloadCallback* routine returns an error or warning NTSTATUS code, such as STATUS_FLT_DO_NOT_DETACH, the minifilter driver is not unloaded. Otherwise, the minifilter driver is unloaded.

* If the FLTFL_FILTER_UNLOAD_MANDATORY flag is set in the *Flags* parameter, the unload operation is mandatory, and the minifilter driver cannot prevent itself from being unloaded.

See [Loading and Unloading](https://docs.microsoft.com/windows-hardware/drivers/ifs/loading-and-unloading) for more information about possible unload causes and the minifilter driver unload process.

## -see-also

[FLT_REGISTRATION](ns-fltkernel-_flt_registration.md)

[FltRegisterFilter](nf-fltkernel-fltregisterfilter.md)

