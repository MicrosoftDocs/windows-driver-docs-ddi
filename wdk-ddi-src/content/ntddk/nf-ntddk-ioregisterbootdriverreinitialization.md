---
UID: NF:ntddk.IoRegisterBootDriverReinitialization
title: IoRegisterBootDriverReinitialization function (ntddk.h)
description: The IoRegisterBootDriverReinitialization routine is called by a boot driver to register the driver's reinitialization routine with the I/O manager to be called after all devices have been enumerated and started.
old-location: kernel\ioregisterbootdriverreinitialization.htm
tech.root: kernel
ms.assetid: af1c1f4b-7710-4cf7-9596-32d11db98abb
ms.date: 04/30/2018
ms.keywords: IoRegisterBootDriverReinitialization, IoRegisterBootDriverReinitialization routine [Kernel-Mode Driver Architecture], k104_492655f7-02ee-48ad-83b8-80ac50716b89.xml, kernel.ioregisterbootdriverreinitialization, ntddk/IoRegisterBootDriverReinitialization
ms.topic: function
req.header: ntddk.h
req.include-header: Ntifs.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoRegisterBootDriverReinitialization
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoRegisterBootDriverReinitialization function


## -description


The <b>IoRegisterBootDriverReinitialization</b> routine is called by a boot driver to register the driver's reinitialization routine with the I/O manager to be called after all devices have been enumerated and started.


## -parameters




### -param DriverObject [in]

Pointer to the driver object for the boot driver to be reinitialized.


### -param DriverReinitializationRoutine [in]

Pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-driver_reinitialize">Reinitialize</a> routine.


### -param Context [in, optional]

Optional context pointer to be passed to the driver's reinitialization routine.


## -returns



None




## -remarks



A boot driver normally calls <b>IoRegisterBootDriverReinitialization</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine, which is run during boot driver initialization. <b>IoRegisterBootDriverReinitialization</b> registers the driver's reinitialization callback routine to be called by the I/O manager after all devices have been enumerated and started. The <i>DriverReinitializationRoutine</i> is run in a system thread at IRQL = PASSIVE_LEVEL. 

A driver should call <b>IoRegisterBootDriverReinitialization</b> only if its <i>DriverEntry</i> routine will return STATUS_SUCCESS. 

If the <i>DriverReinitializationRoutine</i> uses the registry, the <i>DriverEntry</i> routine must include in <b>IoRegisterBootDriverReinitialization</b>'s <i>Context</i> parameter a copy of the string to which <i>DriverEntry</i>'s own <i>RegistryPath</i> parameter points. 

The <i>DriverEntry</i> routine can call <b>IoRegisterBootDriverReinitialization</b> only once. If the reinitialization routine needs to be run more than once, the <i>DriverReinitializationRoutine</i> can call <b>IoRegisterBootDriverReinitialization</b> as many additional times as needed, using the <i>Count</i> parameter to keep track of the number of times the <i>DriverReinitializationRoutine</i> has been called. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-ioregisterdriverreinitialization">IoRegisterDriverReinitialization</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-driver_reinitialize">Reinitialize</a>
 

 

