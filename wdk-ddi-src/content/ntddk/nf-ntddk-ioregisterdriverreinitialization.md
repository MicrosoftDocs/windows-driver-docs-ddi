---
UID: NF:ntddk.IoRegisterDriverReinitialization
title: IoRegisterDriverReinitialization function
author: windows-driver-content
description: The IoRegisterDriverReinitialization routine is called by a driver during its initialization or reinitialization to register its Reinitialize routine to be called again before the driver's and, possibly the system's, initialization is complete.
old-location: kernel\ioregisterdriverreinitialization.htm
old-project: kernel
ms.assetid: bdee26f9-e108-4753-b2e5-a1427212bce9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoRegisterDriverReinitialization routine [Kernel-Mode Driver Architecture], k104_998f1835-132c-49f3-886d-6d78dee35b9d.xml, kernel.ioregisterdriverreinitialization, ntddk/IoRegisterDriverReinitialization, IoRegisterDriverReinitialization
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoRegisterDriverReinitialization
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoRegisterDriverReinitialization function


## -description


The <b>IoRegisterDriverReinitialization</b> routine is called by a driver during its initialization or reinitialization to register its <a href="..\ntddk\nc-ntddk-driver_reinitialize.md">Reinitialize</a> routine to be called again before the driver's and, possibly the system's, initialization is complete.


## -syntax


````
VOID IoRegisterDriverReinitialization(
  _In_     PDRIVER_OBJECT       DriverObject,
  _In_     PDRIVER_REINITIALIZE DriverReinitializationRoutine,
  _In_opt_ PVOID                Context
);
````


## -parameters




### -param DriverObject [in]

Pointer to the driver object that was input to the <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine.


### -param DriverReinitializationRoutine [in]

Pointer to the driver's <a href="..\ntddk\nc-ntddk-driver_reinitialize.md">Reinitialize</a> routine. 


### -param Context [in, optional]

Pointer to the context to be passed to the driver's <i>Reinitialize</i> routine.


## -returns


None



## -remarks


A driver can call this routine only if its <i>DriverEntry</i> routine will return STATUS_SUCCESS. If the driver-supplied <a href="..\ntddk\nc-ntddk-driver_reinitialize.md">Reinitialize</a> routine must use the registry, the <i>DriverEntry</i> routine should include a copy of the string to which  <i>RegistryPath</i> points as part of the context passed to the <i>Reinitialize</i> routine in this call.

If the driver is loaded dynamically, it is possible for this to occur during a normally running system, so all references to the reinitialization queue must be synchronized.

The <i>Count</i> input to a <i>DriverReinitializationRoutine</i> indicates how many times this routine has been called, including the current call.

The <i>DriverEntry</i> routine can call <b>IoRegisterDriverReinitialization</b> only once. If the <i>Reinitialize</i> routine should be run again after any other drivers' <i>Reinitialize</i> routines have returned control, the <i>Reinitialize</i> routine also can call <b>IoRegisterDriverReinitialization</b> as many times as the driver's <i>Reinitialize</i> routine should be run.

Usually, a driver with a <i>Reinitialize</i> routine is a higher-level driver that controls both PnP and legacy devices. Such a driver must not only create device objects for the devices that the PnP manager detects (and for which the PnP manager calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine), the driver must also create device objects for legacy devices that the PnP manager does not detect. A driver can use a <i>Reinitialize</i> routine to create those device objects and layer the driver over the next-lower driver for the underlying device.



## -see-also

<a href="..\ntddk\nf-ntddk-ioregisterbootdriverreinitialization.md">IoRegisterBootDriverReinitialization</a>

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRegisterDriverReinitialization routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

