---
UID: NC:fltkernel.PFLT_INSTANCE_TEARDOWN_CALLBACK
title: PFLT_INSTANCE_TEARDOWN_CALLBACK (fltkernel.h)
description: A minifilter driver can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's InstanceTeardownStartCallback and InstanceTeardownCompleteCallback routines.
old-location: ifsk\pflt_instance_teardown_callback.htm
tech.root: ifsk
ms.date: 07/10/2019
keywords: ["PFLT_INSTANCE_TEARDOWN_CALLBACK callback"]
ms.keywords: FltCallbacks_2bec09ed-3009-465c-842b-67e0cd7d734f.xml, PFLT_INSTANCE_TEARDOWN_CALLBACK, PFLT_INSTANCE_TEARDOWN_CALLBACK function pointer [Installable File System Drivers], fltkernel/PFLT_INSTANCE_TEARDOWN_CALLBACK, ifsk.pflt_instance_teardown_callback
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
targetos: Windows
req.typenames: EXpsFontRestriction
f1_keywords:
 - PFLT_INSTANCE_TEARDOWN_CALLBACK
 - fltkernel/PFLT_INSTANCE_TEARDOWN_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fltkernel.h
api_name:
 - PFLT_INSTANCE_TEARDOWN_CALLBACK
---

# PFLT_INSTANCE_TEARDOWN_CALLBACK callback


## -description

A minifilter driver can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's *InstanceTeardownStartCallback* and *InstanceTeardownCompleteCallback* routines.

## -parameters

### -param FltObjects 

[in]
Pointer to an [FLT_RELATED_OBJECTS](./ns-fltkernel-_flt_related_objects.md) structure that contains opaque pointers for the objects related to the current I/O operation.

### -param Reason 

[in]
Flag that indicates why the minifilter driver instance is being torn down. One of the following:

| Flag | Meaning |
| ---- | ------- |
| FLTFL_INSTANCE_TEARDOWN_FILTER_UNLOAD | The minifilter driver is being unloaded. |
| FLTFL_INSTANCE_TEARDOWN_INTERNAL_ERROR | The system experienced an unexpected internal error. |
| FLTFL_INSTANCE_TEARDOWN_MANDATORY_FILTER_UNLOAD | The minifilter driver is being unloaded. |
| FLTFL_INSTANCE_TEARDOWN_MANUAL | The instance is being detached because a user-mode application has called [**FilterDetach**](/windows/win32/api/fltuser/nf-fltuser-filterdetach) or a kernel-mode component has called [**FltDetachVolume**](./nf-fltkernel-fltdetachvolume.md). |
| FLTFL_INSTANCE_TEARDOWN_VOLUME_DISMOUNT | If set, the volume is being dismounted. (Or the volume has already been dismounted. Or the volume mount operation failed. Or the minifilter driver instance or the volume is being torn down. Or the file system unregistered itself as an active file system.) |

## -remarks

When a minifilter driver registers itself by calling [**FltRegisterFilter**](./nf-fltkernel-fltregisterfilter.md) from its [**DriverEntry**](/windows-hardware/drivers/ifs/writing-a-driverentry-routine-for-a-minifilter-driver) routine, it can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's *InstanceTeardownStartCallback* and *InstanceTeardownCompleteCallback* routines. To register these callback routines, the minifilter driver stores the addresses of the two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK in the **InstanceTeardownStartCallback** and **InstanceTeardownCompleteCallback** members of the [FLT_REGISTRATION](./ns-fltkernel-_flt_registration.md) structure that the minifilter driver passes as the *Registration* parameter of **FltRegisterFilter**.

The *InstanceTeardownStartCallback* and *InstanceTeardownCompleteCallback* routines are optional and can be **NULL**. If the minifilter driver specifies **NULL** for the *InstanceTeardownStartCallback* or *InstanceTeardownCompleteCallback* routine, the instance is still torn down.

The *InstanceTeardownStartCallback* routine is called when the filter manager starts tearing down a minifilter driver instance to allow the minifilter driver to complete any pended I/O operations and save state information.

The *InstanceTeardownStartCallback* routine must:

* Call [**FltCompletePendedPreOperation**](./nf-fltkernel-fltcompletependedpreoperation.md) for each I/O operation that was pended in the minifilter driver's preoperation callback routine to complete the operation or return control of the operation to the filter manager.
* Not pend any new I/O operations. If the minifilter driver uses a callback data queue, it must call [**FltCbdqDisable**](./nf-fltkernel-fltcbdqdisable.md) to disable it.
* Call [**FltCompletePendedPostOperation**](./nf-fltkernel-fltcompletependedpostoperation.md) for each I/O operation that was pended in the minifilter driver's postoperation callback routine to return control of the operation to the filter manager.

The *InstanceTeardownStartCallback* routine can optionally do the following to allow the minifilter driver to unload as quickly as possible:

* Close any opened files.
* Ensure that worker threads perform only the minimum necessary to complete processing of outstanding work items.
* Call [**FltCancelIo**](./nf-fltkernel-fltcancelio.md) to cancel any I/O operations that were initiated by the minifilter driver.
* Stop queuing new work items.

Once the minifilter driver's *InstanceTeardownStartCallback* routine is called, the minifilter driver's preoperation and postoperation callback routines are not called for any new I/O operations. However, they may be called for I/O operations that were started before instance teardown was initiated.

The *InstanceTeardownCompleteCallback* routine is called when the teardown process is complete to allow the minifilter driver to close open files and perform any other necessary cleanup processing.

The *InstanceTeardownCompleteCallback* routine must close any files that were opened by the minifilter driver.

The filter manager calls the minifilter driver's *InstanceTeardownCompleteCallback* routine only after all outstanding I/O operations have been completed or drained.

> [!WARNING] 
> The *InstanceTeardownCompleteCallback* routine will not be called if any of the following conditions are true:
> * There are outstanding pended I/O operations.
> * There are any outstanding I/O operations that were initiated by the minifilter driver.

If the minifilter driver instance is being torn down because the minifilter driver is being unloaded, the unload operation appears to hang until the *InstanceTeardownCompleteCallback* routine returns. To debug these kinds of problems, you should enable the [Driver Verifier](/windows-hardware/drivers/devtest/driver-verifier) on your minifilter driver. The Filter Verifier [I/O Verification](/windows-hardware/drivers/devtest/i-o-verification) option can help identify possible causes, such as unreleased references, that would prevent the minifilter driver from unloading. For more information, see [Filter Verifier](/windows-hardware/drivers/ifs/development-and-testing-tools).

Note that referencing the instance (by calling [**FltObjectReference**](./nf-fltkernel-fltobjectreference.md)) does not prevent the *InstanceTeardownCompleteCallback* routine from being called.

The filter manager calls the *InstanceTeardownStartCallback* and *InstanceTeardownCompleteCallback* routines at IRQL PASSIVE_LEVEL.

## -see-also

[FLT_REGISTRATION](./ns-fltkernel-_flt_registration.md)

[FLT_RELATED_OBJECTS](./ns-fltkernel-_flt_related_objects.md)

[FilterDetach](/windows/win32/api/fltuser/nf-fltuser-filterdetach)

[**FltCancelIo**](./nf-fltkernel-fltcancelio.md)

[**FltCbdqDisable**](./nf-fltkernel-fltcbdqdisable.md)

[**FltCompletePendedPostOperation**](./nf-fltkernel-fltcompletependedpostoperation.md)

[**FltCompletePendedPreOperation**](./nf-fltkernel-fltcompletependedpreoperation.md)

[**FltDetachVolume**](./nf-fltkernel-fltdetachvolume.md)

[**FltObjectReference**](./nf-fltkernel-fltobjectreference.md)

[**FltRegisterFilter**](./nf-fltkernel-fltregisterfilter.md)

[**PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK**](./nc-fltkernel-pflt_instance_query_teardown_callback.md)

[**PFLT_INSTANCE_SETUP_CALLBACK**](./nc-fltkernel-pflt_instance_setup_callback.md)
