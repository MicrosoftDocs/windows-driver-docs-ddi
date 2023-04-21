---
UID: NF:ntddk.IoReportResourceForDetection
title: IoReportResourceForDetection function (ntddk.h)
description: The IoReportResourceForDetection routine claims hardware resources in the configuration registry for a legacy device.
tech.root: kernel
ms.date: 04/20/2023
keywords: ["IoReportResourceForDetection function"]
ms.keywords: IoReportResourceForDetection, IoReportResourceForDetection routine [Kernel-Mode Driver Architecture], k104_e2a8d386-d1bb-4bf5-aa30-d3a905e91174.xml, kernel.ioreportresourcefordetection, ntddk/IoReportResourceForDetection
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - IoReportResourceForDetection
 - ntddk/IoReportResourceForDetection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoReportResourceForDetection
---

## -description

The **IoReportResourceForDetection** routine claims hardware resources in the configuration registry for a legacy device.

## -parameters

### -param DriverObject [in]

Pointer to the driver object that was input to the driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine.

### -param DriverList [in, optional]

Optionally points to a caller-supplied buffer that contains the driver's resource list, if the driver claims the same resources for all its devices. If the caller specifies a *DeviceList*, this parameter is ignored.

### -param DriverListSize [in, optional]

Specifies the size in bytes of an optional *DriverList*. If *DriverList* is **NULL**, this parameter should be zero.

### -param DeviceObject [in, optional]

Optionally points to the device object representing device for which the driver is attempting to claim resources.

### -param DeviceList [in, optional]

Optionally points to a caller-supplied buffer containing the device's resource list. If the driver claims the same resources for all its devices, the caller can specify a *DriverList* instead.

### -param DeviceListSize [in, optional]

Specifies the size in bytes of an optional *DeviceList*. If *DeviceList* is **NULL**, this parameter should be zero.

### -param ConflictDetected [out]

Pointer to a caller-supplied Boolean value that is set to **TRUE** on return if the resources are not available.

## -returns

**IoReportResourceForDetection** returns STATUS_SUCCESS if the resources are claimed. Possible error return values include the following.

| Return code | Description |
|--|--|
| **STATUS_CONFLICTING_ADDRESSES** | The resources could not be claimed because they are already in use or are needed for a PnP-enumerable device. |
| **STATUS_UNSUCCESSFUL** | The *DeviceList* or *DriverList* is invalid. |

## -remarks

This routine is for drivers that detect earlier hardware which cannot be enumerated by Plug and Play (PnP).

If a driver supports only PnP hardware, it does no detection and therefore does not call **IoReportResourceForDetection**. The PnP system enumerates each PnP device, assigns resources to the device, and passes those resources to the device's drivers in an [IRP_MN_START_DEVICE](/windows-hardware/drivers/kernel/irp-mn-start-device) request.

If a PnP driver supports legacy hardware, however, it must call **IoReportResourceForDetection** to claim hardware resources before it attempts to detect the device.

Callers of this routine specify a [**CM_RESOURCE_LIST**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list) in either a *DeviceList* or a *DriverList* that is allocated from paged memory and that consists of raw, untranslated resources. The caller is responsible for freeing the memory.

A driver that can control more than one legacy card at the same time should claim the resources for each device against the device object for the respective device (using the *DeviceObject*, *DeviceList*, and *DeviceListSize* parameters). Such a driver must not claim these resources against their driver object.

A **CM_RESOURCE_LIST** contains two variable-sized arrays. Each array has a default size of one. If either array has more than one element, the caller must allocate memory dynamically to contain the additional elements. Only one [**CM_PARTIAL_RESOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor) can be part of each [**CM_FULL_RESOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_full_resource_descriptor) in the list, except for the last full resource descriptor in the **CM_RESOURCE_LIST**, which can have additional partial resource descriptors in its array.

**IoReportResourceForDetection**, with the help of the PnP manager, determines whether the resources being requested conflict with resources that have already been claimed.

If a conflict is detected, this routine sets the BOOLEAN at *ConflictDetected* to **TRUE** and returns STATUS_CONFLICTING_ADDRESSES.

If no conflict is detected, this routine claims the resources, sets the BOOLEAN at *ConflictDetected* to **FALSE**, and returns STATUS_SUCCESS.

If this routine succeeds and the driver detects a legacy device, the driver reports the device to the PnP manager by calling [IoReportDetectedDevice](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreportdetecteddevice). In that call, the driver sets *ResourceAssigned* to **TRUE** so the PnP manager does not attempt to claim the resources again.

When a driver no longer requires the resources claimed by a call to this routine, the driver calls this routine again with a *DriverList* or *DeviceList* with a **Count** of zero.

If a driver claims resources on a device-specific basis for more than one device, the driver must call this routine for each such device.

A driver can call this routine more than once for a given device. If one set of resources fails, the driver can call the routine again for the same device with a different set of resources. If a set of resources succeeds, the driver can call this routine again with a new list; the new list replaces the previous list.

Callers of **IoReportResourceForDetection** must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.

## -see-also

[**CM_RESOURCE_LIST**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list)

[IoReportDetectedDevice](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreportdetecteddevice)
