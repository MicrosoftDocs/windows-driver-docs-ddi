---
UID: NC:fltkernel.PFLT_INSTANCE_TEARDOWN_CALLBACK
title: PFLT_INSTANCE_TEARDOWN_CALLBACK (fltkernel.h)
description: A minifilter driver can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's InstanceTeardownStartCallback and InstanceTeardownCompleteCallback routines.
old-location: ifsk\pflt_instance_teardown_callback.htm
tech.root: ifsk
ms.assetid: d2f87c47-7f26-4c22-a5b8-2be8f309d1ba
ms.date: 07/10/2019
ms.keywords: FltCallbacks_2bec09ed-3009-465c-842b-67e0cd7d734f.xml, PFLT_INSTANCE_TEARDOWN_CALLBACK, PFLT_INSTANCE_TEARDOWN_CALLBACK function pointer [Installable File System Drivers], fltkernel/PFLT_INSTANCE_TEARDOWN_CALLBACK, ifsk.pflt_instance_teardown_callback
ms.topic: callback
f1_keywords:
 - "fltkernel/PFLT_INSTANCE_TEARDOWN_CALLBACK"
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- fltkernel.h
api_name:
- PFLT_INSTANCE_TEARDOWN_CALLBACK
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_INSTANCE_TEARDOWN_CALLBACK callback

## -description

A minifilter driver can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's *InstanceTeardownStartCallback* and *InstanceTeardownCompleteCallback* routines.

## -parameters

### -param FltObjects [in]

Pointer to an [FLT_RELATED_OBJECTS](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects) structure that contains opaque pointers for the objects related to the current I/O operation.

### -param Reason [in]

Flag that indicates why the minifilter driver instance is being torn down. One of the following:

| Flag | Meaning |
| ---- | ------- |
| FLTFL_INSTANCE_TEARDOWN_FILTER_UNLOAD | The minifilter driver is being unloaded. |
| FLTFL_INSTANCE_TEARDOWN_INTERNAL_ERROR | The system experienced an unexpected internal error. |
| FLTFL_INSTANCE_TEARDOWN_MANDATORY_FILTER_UNLOAD | The minifilter driver is being unloaded. |
| FLTFL_INSTANCE_TEARDOWN_MANUAL | The instance is being detached because a user-mode application has called [**FilterDetach**](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterdetach) or a kernel-mode component has called [**FltDetachVolume**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdetachvolume). |
| FLTFL_INSTANCE_TEARDOWN_VOLUME_DISMOUNT | If set, the volume is being dismounted. (Or the volume has already been dismounted. Or the volume mount operation failed. Or the minifilter driver instance or the volume is being torn down. Or the file system unregistered itself as an active file system.) |

## -remarks

When a minifilter driver registers itself by calling [**FltRegisterFilter**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter) from its [**DriverEntry**](https://docs.microsoft.com/windows-hardware/drivers/ifs/writing-a-driverentry-routine-for-a-minifilter-driver) routine, it can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's *InstanceTeardownStartCallback* and *InstanceTeardownCompleteCallback* routines. To register these callback routines, the minifilter driver stores the addresses of the two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK in the **InstanceTeardownStartCallback** and **InstanceTeardownCompleteCallback** members of the [FLT_REGISTRATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration) structure that the minifilter driver passes as the *Registration* parameter of **FltRegisterFilter**.

The *InstanceTeardownStartCallback* and *InstanceTeardownCompleteCallback* routines are optional and can be **NULL**. If the minifilter driver specifies **NULL** for the *InstanceTeardownStartCallback* or *InstanceTeardownCompleteCallback* routine, the instance is still torn down.

The *InstanceTeardownStartCallback* routine is called when the filter manager starts tearing down a minifilter driver instance to allow the minifilter driver to complete any pended I/O operations and save state information.

The *InstanceTeardownStartCallback* routine must:

* Call [**FltCompletePendedPreOperation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpreoperation) for each I/O operation that was pended in the minifilter driver's preoperation callback routine to complete the operation or return control of the operation to the filter manager.
* Not pend any new I/O operations. If the minifilter driver uses a callback data queue, it must call [**FltCbdqDisable**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqdisable) to disable it.
* Call [**FltCompletePendedPostOperation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpostoperation) for each I/O operation that was pended in the minifilter driver's postoperation callback routine to return control of the operation to the filter manager.

The *InstanceTeardownStartCallback* routine can optionally do the following to allow the minifilter driver to unload as quickly as possible:

* Close any opened files.
* Ensure that worker threads perform only the minimum necessary to complete processing of outstanding work items.
* Call [**FltCancelIo**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelio) to cancel any I/O operations that were initiated by the minifilter driver.
* Stop queuing new work items.

Once the minifilter driver's *InstanceTeardownStartCallback* routine is called, the minifilter driver's preoperation and postoperation callback routines are not called for any new I/O operations. However, they may be called for I/O operations that were started before instance teardown was initiated.

The *InstanceTeardownCompleteCallback* routine is called when the teardown process is complete to allow the minifilter driver to close open files and perform any other necessary cleanup processing.

The *InstanceTeardownCompleteCallback* routine must close any files that were opened by the minifilter driver.

The filter manager calls the minifilter driver's *InstanceTeardownCompleteCallback* routine only after all outstanding I/O operations have been completed or drained.

> [!WARNING] 
> The *InstanceTeardownCompleteCallback* routine will not be called if any of the following conditions are true:
> * There are outstanding pended I/O operations.
> * There are any outstanding I/O operations that were initiated by the minifilter driver.

If the minifilter driver instance is being torn down because the minifilter driver is being unloaded, the unload operation appears to hang until the *InstanceTeardownCompleteCallback* routine returns. To debug these kinds of problems, you should enable the [Driver Verifier](https://docs.microsoft.com/windows-hardware/drivers/devtest/driver-verifier) on your minifilter driver. The Filter Verifier [I/O Verification](https://docs.microsoft.com/windows-hardware/drivers/devtest/i-o-verification) option can help identify possible causes, such as unreleased references, that would prevent the minifilter driver from unloading. For more information, see [Filter Verifier](https://docs.microsoft.com/windows-hardware/drivers/ifs/development-and-testing-tools).

Note that referencing the instance (by calling [**FltObjectReference**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectreference)) does not prevent the *InstanceTeardownCompleteCallback* routine from being called.

The filter manager calls the *InstanceTeardownStartCallback* and *InstanceTeardownCompleteCallback* routines at IRQL PASSIVE_LEVEL.

## -see-also

[FLT_REGISTRATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration)

[FLT_RELATED_OBJECTS](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects)

[FilterDetach](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterdetach)

[**FltCancelIo**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelio)

[**FltCbdqDisable**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqdisable)

[**FltCompletePendedPostOperation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpostoperation)

[**FltCompletePendedPreOperation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpreoperation)

[**FltDetachVolume**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdetachvolume)

[**FltObjectReference**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectreference)

[**FltRegisterFilter**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter)

[**PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_query_teardown_callback)

[**PFLT_INSTANCE_SETUP_CALLBACK**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_setup_callback)
