---
UID: NF:ntddk.IoRegisterDriverReinitialization
title: IoRegisterDriverReinitialization function (ntddk.h)
description: The IoRegisterDriverReinitialization routine is called by a driver during its initialization or reinitialization to register its Reinitialize routine to be called again before the driver's and, possibly the system's, initialization is complete.
old-location: kernel\ioregisterdriverreinitialization.htm
tech.root: kernel
ms.assetid: bdee26f9-e108-4753-b2e5-a1427212bce9
ms.date: 04/30/2018
keywords: ["IoRegisterDriverReinitialization function"]
ms.keywords: IoRegisterDriverReinitialization, IoRegisterDriverReinitialization routine [Kernel-Mode Driver Architecture], k104_998f1835-132c-49f3-886d-6d78dee35b9d.xml, kernel.ioregisterdriverreinitialization, ntddk/IoRegisterDriverReinitialization
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoRegisterDriverReinitialization
 - ntddk/IoRegisterDriverReinitialization
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoRegisterDriverReinitialization
---

# IoRegisterDriverReinitialization function


## -description

The <b>IoRegisterDriverReinitialization</b> routine is called by a driver during its initialization or reinitialization to register its <a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-driver_reinitialize">Reinitialize</a> routine to be called again before the driver's and, possibly the system's, initialization is complete.

## -parameters

### -param DriverObject 

[in]
Pointer to the driver object that was input to the <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine.

### -param DriverReinitializationRoutine 

[in]
Pointer to the driver's <a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-driver_reinitialize">Reinitialize</a> routine.

### -param Context 

[in, optional]
Pointer to the context to be passed to the driver's <i>Reinitialize</i> routine.

## -remarks

A driver can call this routine only if its <i>DriverEntry</i> routine will return STATUS_SUCCESS. If the driver-supplied <a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-driver_reinitialize">Reinitialize</a> routine must use the registry, the <i>DriverEntry</i> routine should include a copy of the string to which  <i>RegistryPath</i> points as part of the context passed to the <i>Reinitialize</i> routine in this call.

If the driver is loaded dynamically, it is possible for this to occur during a normally running system, so all references to the reinitialization queue must be synchronized.

The <i>Count</i> input to a <i>DriverReinitializationRoutine</i> indicates how many times this routine has been called, including the current call.

The <i>DriverEntry</i> routine can call <b>IoRegisterDriverReinitialization</b> only once. If the <i>Reinitialize</i> routine should be run again after any other drivers' <i>Reinitialize</i> routines have returned control, the <i>Reinitialize</i> routine also can call <b>IoRegisterDriverReinitialization</b> as many times as the driver's <i>Reinitialize</i> routine should be run.

Usually, a driver with a <i>Reinitialize</i> routine is a higher-level driver that controls both PnP and legacy devices. Such a driver must not only create device objects for the devices that the PnP manager detects (and for which the PnP manager calls the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine), the driver must also create device objects for legacy devices that the PnP manager does not detect. A driver can use a <i>Reinitialize</i> routine to create those device objects and layer the driver over the next-lower driver for the underlying device.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioregisterbootdriverreinitialization">IoRegisterBootDriverReinitialization</a>