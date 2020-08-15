---
UID: NF:ntddk.IoReportResourceForDetection
title: IoReportResourceForDetection function (ntddk.h)
description: The IoReportResourceForDetection routine claims hardware resources in the configuration registry for a legacy device.
old-location: kernel\ioreportresourcefordetection.htm
tech.root: kernel
ms.assetid: 83b8e0b0-112c-4263-91f8-0c2e20dd76a4
ms.date: 04/30/2018
keywords: ["IoReportResourceForDetection function"]
ms.keywords: IoReportResourceForDetection, IoReportResourceForDetection routine [Kernel-Mode Driver Architecture], k104_e2a8d386-d1bb-4bf5-aa30-d3a905e91174.xml, kernel.ioreportresourcefordetection, ntddk/IoReportResourceForDetection
f1_keywords:
 - "ntddk/IoReportResourceForDetection"
 - "IoReportResourceForDetection"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoReportResourceForDetection
targetos: Windows
req.typenames: 
---

# IoReportResourceForDetection function


## -description


The <b>IoReportResourceForDetection</b> routine claims hardware resources in the configuration registry for a legacy device.


## -parameters




### -param DriverObject 
[in]
Pointer to the driver object that was input to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine.


### -param DriverList 
[in, optional]
Optionally points to a caller-supplied buffer that contains the driver's resource list, if the driver claims the same resources for all its devices. If the caller specifies a <i>DeviceList</i>, this parameter is ignored.


### -param DriverListSize 
[in, optional]
Specifies the size in bytes of an optional <i>DriverList</i>. If <i>DriverList</i> is <b>NULL</b>, this parameter should be zero.


### -param DeviceObject 
[in, optional]
Optionally points to the device object representing device for which the driver is attempting to claim resources. 


### -param DeviceList 
[in, optional]
Optionally points to a caller-supplied buffer containing the device's resource list. If the driver claims the same resources for all its devices, the caller can specify a <i>DriverList</i> instead. 


### -param DeviceListSize 
[in, optional]
Specifies the size in bytes of an optional <i>DeviceList</i>. If <i>DeviceList</i> is <b>NULL</b>, this parameter should be zero. 


### -param ConflictDetected 
[out]
Pointer to a caller-supplied Boolean value that is set to <b>TRUE</b> on return if the resources are not available. 


## -returns



<b>IoReportResourceForDetection</b> returns STATUS_SUCCESS if the resources are claimed. Possible error return values include the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONFLICTING_ADDRESSES</b></dt>
</dl>
</td>
<td width="60%">
The resources could not be claimed because they are already in use or are needed for a PnP-enumerable device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The <i>DeviceList</i> or <i>DriverList</i> is invalid.

</td>
</tr>
</table>
 




## -remarks



This routine is for drivers that detect earlier hardware which cannot be enumerated by Plug and Play (PnP).

If a driver supports only PnP hardware, it does no detection and therefore does not call <b>IoReportResourceForDetection</b>. The PnP system enumerates each PnP device, assigns resources to the device, and passes those resources to the device's drivers in an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> request.

If a PnP driver supports legacy hardware, however, it must call <b>IoReportResourceForDetection</b> to claim hardware resources before it attempts to detect the device.

Callers of this routine specify a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a> in either a <i>DeviceList</i> or a <i>DriverList</i> that is allocated from paged memory and that consists of raw, untranslated resources. The caller is responsible for freeing the memory. 

A driver that can control more than one legacy card at the same time should claim the resources for each device against the device object for the respective device (using the <i>DeviceObject</i>, <i>DeviceList</i>, and <i>DeviceListSize</i> parameters). Such a driver must not claim these resources against their driver object.

A <b>CM_RESOURCE_LIST</b> contains two variable-sized arrays. Each array has a default size of one. If either array has more than one element, the caller must allocate memory dynamically to contain the additional elements. Only one <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> can be part of each <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_full_resource_descriptor">CM_FULL_RESOURCE_DESCRIPTOR</a> in the list, except for the last full resource descriptor in the <b>CM_RESOURCE_LIST</b>, which can have additional partial resource descriptors in its array.

<b>IoReportResourceForDetection</b>, with the help of the PnP manager, determines whether the resources being requested conflict with resources that have already been claimed.

If a conflict is detected, this routine sets the BOOLEAN at <i>ConflictDetected</i> to <b>TRUE</b> and returns STATUS_CONFLICTING_ADDRESSES. 

If no conflict is detected, this routine claims the resources, sets the BOOLEAN at <i>ConflictDetected</i> to <b>FALSE</b>, and returns STATUS_SUCCESS.

If this routine succeeds and the driver detects a legacy device, the driver reports the device to the PnP manager by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreportdetecteddevice">IoReportDetectedDevice</a>. In that call, the driver sets <i>ResourceAssigned</i> to <b>TRUE</b> so the PnP manager does not attempt to claim the resources again.

When a driver no longer requires the resources claimed by a call to this routine, the driver calls this routine again with a <i>DriverList</i> or <i>DeviceList</i> with a <b>Count</b> of zero.

If a driver claims resources on a device-specific basis for more than one device, the driver must call this routine for each such device.

A driver can call this routine more than once for a given device. If one set of resources fails, the driver can call the routine again for the same device with a different set of resources. If a set of resources succeeds, the driver can call this routine again with a new list; the new list replaces the previous list.

Callers of <b>IoReportResourceForDetection</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreportdetecteddevice">IoReportDetectedDevice</a>
 

 

