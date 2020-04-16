---
UID: NC:fltkernel.PFLT_INSTANCE_SETUP_CALLBACK
title: PFLT_INSTANCE_SETUP_CALLBACK (fltkernel.h)
description: A minifilter driver can register a routine of type PFLT_INSTANCE_SETUP_CALLBACK as the minifilter driver's InstanceSetupCallback routine.
old-location: ifsk\pflt_instance_setup_callback.htm
tech.root: ifsk
ms.assetid: bbdd393d-3f0f-4bbd-8a74-ed75d20b0433
ms.date: 05/10/2019
keywords: ["PFLT_INSTANCE_SETUP_CALLBACK callback function"]
ms.keywords: FltCallbacks_c32f2452-6198-4e87-8566-6e219dcf2f28.xml, InstanceSetupCallback, InstanceSetupCallback routine [Installable File System Drivers], PFLT_INSTANCE_SETUP_CALLBACK, fltkernel/InstanceSetupCallback, ifsk.pflt_instance_setup_callback
f1_keywords:
 - "fltkernel/InstanceSetupCallback"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- fltkernel.h
api_name:
- InstanceSetupCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFLT_INSTANCE_SETUP_CALLBACK callback function

## -description

A minifilter driver can register a routine of type PFLT_INSTANCE_SETUP_CALLBACK as the minifilter driver's *InstanceSetupCallback* routine.

## -parameters

### -param FltObjects [in]

Pointer to an [FLT_RELATED_OBJECTS](ns-fltkernel-_flt_related_objects.md) structure that contains opaque pointers for the objects related to the current operation.

### -param Flags [in]

Bitmask of flags that indicate why the instance is being attached. Can be one or more of the following:

| Flag | Meaning |
| ---- | ------- |
| FLTFL_INSTANCE_SETUP_AUTOMATIC_ATTACHMENT | The instance is being attached automatically. Either the minifilter driver was just loaded and is being attached to all existing volumes, or it is being attached to a newly mounted volume. |
| FLTFL_INSTANCE_SETUP_MANUAL_ATTACHMENT | The instance is being attached manually because a user-mode application has called [FilterAttach](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterattach) or [FilterAttachAtAltitude](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterattachataltitude), or because a kernel-mode component has called [FltAttachVolume](nf-fltkernel-fltattachvolume.md) or [FltAttachVolumeAtAltitude](nf-fltkernel-fltattachvolumeataltitude.md) |
| FLTFL_INSTANCE_SETUP_NEWLY_MOUNTED_VOLUME | The instance is being attached automatically to a newly mounted volume. |
| FLTFL_INSTANCE_SETUP_DETACHED_VOLUME | The instance is being attached to a detached volume. It is possible, on some file systems (such as FAT and CDFS, which are used by some removable media drives), to reattach a volume after it has detached. A volume is detached if it has no associated storage stack. A volume in this state is usually a dismounted volume that still has open files. |

### -param VolumeDeviceType [in]

Device type of the file system volume. Must be one of the following:

* FILE_DEVICE_CD_ROM_FILE_SYSTEM
* FILE_DEVICE_DISK_FILE_SYSTEM
* FILE_DEVICE_NETWORK_FILE_SYSTEM

### -param VolumeFilesystemType [in]

File system type of the volume. The possible values are listed in [FLT_FILESYSTEM_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ne-fltuserstructures-_flt_filesystem_type).

## -returns

This callback routine returns STATUS_SUCCESS or an NTSTATUS value such as the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DO_NOT_ATTACH | Returning this value prevents the minifilter driver instance from being attached to the given volume. This is an error code. |

## -remarks

<div class="alert"><b>Note</b>   Do not perform any thread synchronization or inter-process communication in the PFLT_INSTANCE_SETUP_CALLBACK implementation. Performing such operations can lead to deadlock conditions. </div>

When a minifilter driver registers itself by calling [FltRegisterFilter](nf-fltkernel-fltregisterfilter.md) from its [DriverEntry](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_initialize) routine, it can register a routine of type PFLT_INSTANCE_SETUP_CALLBACK as the minifilter driver's *InstanceSetupCallback* routine.

To register the *InstanceSetupCallback* routine, the minifilter driver stores the address of a routine of type PFLT_INSTANCE_SETUP_CALLBACK in the **InstanceSetupCallback** member of the [FLT_REGISTRATION](ns-fltkernel-_flt_registration.md) structure that the minifilter driver passes as the *Registration* parameter of **FltRegisterFilter**.

The filter manager calls this routine on the first operation after a new volume is mounted.

The filter manager calls this routine to allow the minifilter driver to respond to an automatic or manual attachment request. If this routine returns an error or warning NTSTATUS code, the minifilter driver instance is not attached to the given volume. Otherwise, the minifilter driver instance is attached to the given volume.

## -see-also

[FLT_REGISTRATION](ns-fltkernel-_flt_registration.md)

[FLT_RELATED_OBJECTS](ns-fltkernel-_flt_related_objects.md)

[FilterAttach](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterattach)

[FilterAttachAtAltitude](https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterattachataltitude)

[FltAttachVolume](nf-fltkernel-fltattachvolume.md)

[FltAttachVolumeAtAltitude](nf-fltkernel-fltattachvolumeataltitude.md)

[FltRegisterFilter](nf-fltkernel-fltregisterfilter.md)

[PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK](nc-fltkernel-pflt_instance_query_teardown_callback.md)

[PFLT_INSTANCE_TEARDOWN_CALLBACK](nc-fltkernel-pflt_instance_teardown_callback.md)
