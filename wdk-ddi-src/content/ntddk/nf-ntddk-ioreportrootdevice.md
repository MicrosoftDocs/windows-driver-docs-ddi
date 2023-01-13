---
UID: NF:ntddk.IoReportRootDevice
title: IoReportRootDevice function (ntddk.h)
description: The IoReportRootDevice routine reports a device that cannot be detected by a PnP bus driver to the PnP Manager. IoReportRootDevice allows only one device per driver to be created.
tech.root: kernel
ms.date: 12/06/2022
keywords: ["IoReportRootDevice function"]
ms.keywords: IoReportRootDevice, IoReportRootDevice routine [Kernel-Mode Driver Architecture], kernel.ioreportrootdevice, ntddk/IoReportRootDevice
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
 - IoReportRootDevice
 - ntddk/IoReportRootDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoReportRootDevice
---

## -description

The **IoReportRootDevice** routine reports a device that cannot be detected by a PnP bus driver to the PnP Manager.  **IoReportRootDevice** allows only one device per driver to be created.

## -parameters

### -param DriverObject [in]

Pointer to the driver object of the driver that detected the device.

## -returns

**IoReportRootDevice** returns STATUS_SUCCESS on success, or the appropriate error code on failure.

## -remarks

Drivers for devices that cannot be detected by a PnP bus driver use **IoReportRootDevice** to report their device to the system. Devices that can be detected by a PnP bus driver should be reported in response to an [IRP_MN_QUERY_DEVICE_RELATIONS](/windows-hardware/drivers/kernel/irp-mn-query-device-relations) request.

A driver typically calls this routine from its [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine.

**IoReportRootDevice** marks the device as a root-enumerated device and this identification is persistent across system boots. The PnP manager "detects" the device on the root-enumerated list and configures it like a PnP device: the PnP manager queries for device information, identifies the appropriate drivers and calls their *AddDevice* routines, and sends all the appropriate PnP IRPs.

The system generates a single Hardware ID string for the device, of the form ROOT\\*Driver* where *Driver*  is the driver's service name. A driver can provide additional hardware IDs or compatible IDs by handling the [IRP_MN_QUERY_ID](/windows-hardware/drivers/kernel/irp-mn-query-id) request.

A driver writer must provide an INF file that matches any of the specified hardware IDs or compatible IDs. The INF file should specify the original driver that called **IoReportRootDevice** as the driver to load for those IDs. The system uses this information to rebuild the driver stack for the device, for example on restart. Callers of **IoReportRootDevice** must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.

Drivers should use [IoReportDetectedDevice](./nf-ntddk-ioreportdetecteddevice.md) to report hardware devices that use resources but cannot be detected by a PnP bus driver instead of **IoReportRootDevice**.

## -see-also

[AddDevice](../wdm/nc-wdm-driver_add_device.md)

[DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver)

[IRP_MN_QUERY_DEVICE_RELATIONS](/windows-hardware/drivers/kernel/irp-mn-query-device-relations)

[IRP_MN_QUERY_ID](/windows-hardware/drivers/kernel/irp-mn-query-id)

[IRP_MN_START_DEVICE](/windows-hardware/drivers/kernel/irp-mn-start-device)

[IoReportDetectedDevice](./nf-ntddk-ioreportdetecteddevice.md)

[IoReportResourceForDetection](./nf-ntddk-ioreportresourcefordetection.md)