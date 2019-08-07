---
UID: TP:kernel
title: Windows kernel
ms.assetid: f7c71d77-9a5b-3320-80a1-302b75314d1e
ms.date: 05/09/2018
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
author: tedhudek
product:
- Windows
ms.custom: 19H1
---

# Windows kernel

## -description
Standard driver routines must be implemented by your driver. Driver support routines are routines that the Windows operating system provides. Drivers do not use Microsoft Win32 routines; instead, they use the driver support routines that this section describes.
The driver support routines in this section are organized by kernel-mode managers and libraries.

- Standard Driver Routines
Here are the required and optional routines that you must implement in your driver to respond to calls from Windows or other drivers. When these routines are called, your code must respond to the call and return the appropriate data in a timely manner.

    The following routines are required for all drivers:

    -    [DriverEntry](../wdm/nc-wdm-driver_initialize.md)
    -    [AddDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_add_device)
    -    [DispatchXxx (routines beginning with "Dispatch" such as DispatchCreate)](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_dispatch) 
    -    [DriverUnload](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_unload)

    The other routines are optional, but you may need to implement them depending on your driver type and the location of your driver in the device stack.

    For more information about standard driver routines, see [Introduction to Standard Driver Routines](https://docs.microsoft.com/windows-hardware/drivers/kernel/introduction-to-standard-driver-routines).

- Driver Support Routines

    Driver support routines are routines that the Windows operating system provides for kernel-mode drivers to use. Drivers do not use Microsoft Win32 routines; instead, they use the driver support routines that this section describes.

    The driver support routines in this section are organized by kernel-mode managers and libraries.

    The following kernel-mode managers provide support for drivers:

    -    Object Manager Routines
    -    Memory Manager Routines
    -    Process and Thread Manager Routines
    -    I/O Manager Routines
    -    Power Manager Routines
    -    Configuration Manager Routines
    -    Kernel Transaction Manager Routines
    -    Security Reference Monitor Routines

    The following kernel-mode libraries provide support for drivers:

    -    Core Kernel Library Support Routines
    -    Executive Library Support Routines
    -    Run-Time Library (RTL) Routines
    -    Safe String Library Routines
    -    Safe Integer Library Routines
    -    Direct Memory Access (DMA) Library Routines
    -    Hardware Abstraction Layer (HAL) Library Routines
    -    Common Log File System (CLFS) Routines
    -    Windows Management Instrumentation (WMI) Library Support Routines
    -    ZwXxx Routines
    -    Auxiliary Kernel-Mode Library Routines and Structures
    -    Processor Group Compatibility Library


### Public Headers for Windows Kernel
To develop Windows kernel, you need these headers:

 * [aux_klib.h](../aux_klib/index.md)
 * [buffring.h](../buffring/index.md)
 * [hwnclx.h](../hwnclx/index.md)
 * [ioaccess.h](../ioaccess/index.md)
 * [iointex.h](../iointex/index.md)
 * [ntddk.h](../ntddk/index.md)
 * [ntddsfio.h](../ntddsfio/index.md)
 * [ntddsysenv.h](../ntddsysenv/index.md)
 * [ntimage.h](../ntimage/index.md)
 * [ntintsafe.h](../ntintsafe/index.md)
 * [ntpoapi.h](../ntpoapi/index.md)
 * [ntstrsafe.h](../ntstrsafe/index.md)
 * [pcivirt.h](../pcivirt/index.md)
 * [pep_x.h](../pep_x/index.md)
 * [pepevents.h](../pepevents/index.md)
 * [pepfx.h](../pepfx/index.md)
 * [procgrp.h](../procgrp/index.md)
 * [pwmutil.h](../pwmutil/index.md)
 * [vpci.h](../vpci/index.md)
 * [wdm.h](../wdm/index.md)
 * [wdmsec.h](../wdmsec/index.md)
 * [wmidata.h](../wmidata/index.md)
 * [wmilib.h](../wmilib/index.md)
 * [wmistr.h](../wmistr/index.md)

For the programming guide, see [Windows kernel](https://docs.microsoft.com/windows-hardware/drivers/kernel).




## Initialization and Unload

This section summarizes kernel-mode support routines that can be called by drivers from their DriverEntry, AddDevice, Reinitialize, or Unload routines.

|**Routines for …**  | **Routine** |
|:--|:--|
| Obtaining and reporting hardware configuration information about a driver's devices and the current platform. | [**IoGetDeviceProperty**](../wdm/nf-wdm-iogetdeviceproperty.md), [**IoReportDetectedDevice**](../ntddk/nf-ntddk-ioreportdetecteddevice.md), [**IoReportResourceForDetection**](../ntddk/nf-ntddk-ioreportresourcefordetection.md), [**IoGetDmaAdapter**](../wdm/nf-wdm-iogetdmaadapter.md), [**IoGetConfigurationInformation**](../ntddk/nf-ntddk-iogetconfigurationinformation.md), [**HalExamineMBR**](../ntddk/nf-ntddk-halexaminembr.md), [**IoReadPartitionTable**](../wdm/nf-wdm-file:///C:\Docs\kernel\storage\ioreadpartitiontable.md), [**IoInvalidateDeviceRelations**](../wdm/nf-wdm-ioinvalidatedevicerelations.md), [**IoInvalidateDeviceState**](../wdm/nf-wdm-ioinvalidatedevicestate.md), [**IoRegisterPlugPlayNotification**](../wdm/nf-wdm-ioregisterplugplaynotification.md), [**IoUnregisterPlugPlayNotification**](../wdm/nf-wdm-iounregisterplugplaynotification.md), [**IoRequestDeviceEject**](../wdm/nf-wdm-iorequestdeviceeject.md), [**IoReportTargetDeviceChange**](../wdm/nf-wdm-ioreporttargetdevicechange.md)
| Obtaining and reporting configuration information, and for registering interfaces in the registry. | [**IoGetDeviceProperty**](../wdm/nf-wdm-iogetdeviceproperty.md), [****IoOpenDeviceInterfaceRegistryKey****](../wdm/nf-wdm-ioopendeviceinterfaceregistrykey.md), [****IoOpenDeviceRegistryKey****](../wdm/nf-wdm-ioopendeviceregistrykey.md), [**IoRegisterDeviceInterface**](../wdm/nf-wdm-ioregisterdeviceinterface.md), [**IoSetDeviceInterfaceState**](../wdm/nf-wdm-iosetdeviceinterfacestate.md), [**RtlCheckRegistryKey**](../wdm/nf-wdm-rtlcheckregistrykey.md), [**RtlCreateRegistryKey**](../wdm/nf-wdm-rtlcreateregistrykey.md), [**RtlQueryRegistryValues**](../wdm/nf-wdm-rtlqueryregistryvalues.md), [**RtlWriteRegistryValue**](../wdm/nf-wdm-rtlwriteregistryvalue.md), [**RtlDeleteRegistryValue**](../wdm/nf-wdm-rtldeleteregistryvalue.md), [**InitializeObjectAttributes**](https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes), [**ZwCreateKey**](../wdm/nf-wdm-zwcreatekey.md), [**ZwOpenKey**](../wdm/nf-wdm-zwopenkey.md), [**ZwQueryKey**](../wdm/nf-wdm-zwquerykey.md), [**ZwEnumerateKey**](../wdm/nf-wdm-zwenumeratekey.md), [**ZwEnumerateValueKey**](../wdm/nf-wdm-zwenumeratevaluekey.md), [**ZwQueryValueKey**](../wdm/nf-wdm-zwqueryvaluekey.md), [**ZwSetValueKey**](../wdm/nf-wdm-zwsetvaluekey.md), [**ZwFlushKey**](../wdm/nf-wdm-zwflushkey.md), [**ZwDeleteKey**](../wdm/nf-wdm-zwdeletekey.md), [**ZwClose**](../wdm/nf-wdm-zwclose.md) | 
| Setting up and freeing the objects and resources that drivers might use. | [**IoCreateDevice**](../wdm/nf-wdm-iocreatedevice.md), [**IoDeleteDevice**](../wdm/nf-wdm-iodeletedevice.md), [**IoGetDeviceObjectPointer**](../wdm/nf-wdm-iogetdeviceobjectpointer.md), [**IoAttachDeviceToDeviceStack**](../wdm/nf-wdm-ioattachdevicetodevicestack.md), [**IoGetAttachedDeviceReference**](../wdm/nf-wdm-iogetattacheddevicereference.md), [**IoDetachDevice**](../wdm/nf-wdm-iodetachdevice.md), [**IoAllocateDriverObjectExtension**](../wdm/nf-wdm-ioallocatedriverobjectextension.md), [**IoGetDriverObjectExtension**](../wdm/nf-wdm-iogetdriverobjectextension.md), [**IoRegisterDeviceInterface**](../wdm/nf-wdm-ioregisterdeviceinterface.md), [**IoIsWdmVersionAvailable**](../wdm/nf-wdm-ioiswdmversionavailable.md), [**IoDeleteSymbolicLink**](../wdm/nf-wdm-iodeletesymboliclink.md), [**IoAssignArcName**](../ntddk/nf-ntddk-ioassignarcname.md), [**IoDeassignArcName**](../ntddk/nf-ntddk-iodeassignarcname.md), [**IoSetShareAccess**](../wdm/nf-wdm-iosetshareaccess.md), [**IoConnectInterrupt**](../wdm/nf-wdm-ioconnectinterrupt.md), [**IoDisconnectInterrupt**](../wdm/nf-wdm-iodisconnectinterrupt.md), [**IoConnectInterruptEx**](../wdm/nf-wdm-ioconnectinterruptex.md), [**IoDisconnectInterruptEx**](../wdm/nf-wdm-iodisconnectinterruptex.md), [**IoInitializeDpcRequest**](../wdm/nf-wdm-ioinitializedpcrequest.md), [**IoReadPartitionTable**](../wdm/nf-wdm-file:///C:\Docs\kernel\storage\ioreadpartitiontable.md), [**IoSetPartitionInformation**](../wdm/nf-wdm-file:///C:\Docs\kernel\storage\iosetpartitioninformation.md), [**IoWritePartitionTable**](../wdm/nf-wdm-file:///C:\Docs\kernel\storage\iowritepartitiontable.md), [**IoCreateController**](../ntddk/nf-ntddk-iocreatecontroller.md), [**IoDeleteController**](../ntddk/nf-ntddk-iodeletecontroller.md), [**KeInitializeSpinLock**](../wdm/nf-wdm-keinitializespinlock.md), [**KeInitializeDpc**](../wdm/nf-wdm-keinitializedpc.md), [**KeInitializeTimer**](../wdm/nf-wdm-keinitializetimer.md), [**KeInitializeTimerEx**](../wdm/nf-wdm-keinitializetimerex.md), [**KeInitializeEvent**](../wdm/nf-wdm-keinitializeevent.md), [**ExInitializeFastMutex**](../wdm/nf-wdm-exinitializefastmutex.md), [**KeInitializeMutex**](../wdm/nf-wdm-keinitializemutex.md), [**KeInitializeSemaphore**](../wdm/nf-wdm-keinitializesemaphore.md), [**IoCreateNotificationEvent**](../wdm/nf-wdm-iocreatenotificationevent.md), [**IoCreateSynchronizationEvent**](../wdm/nf-wdm-iocreatesynchronizationevent.md), [**PsCreateSystemThread**](../wdm/nf-wdm-pscreatesystemthread.md), [**PsTerminateSystemThread**](../wdm/nf-wdm-psterminatesystemthread.md), [**KeSetBasePriorityThread**](../ntddk/nf-ntddk-kesetbaseprioritythread.md), [**KeSetPriorityThread**](../wdm/nf-wdm-kesetprioritythread.md), [**MmIsThisAnNtAsSystem**](../ntddk/nf-ntddk-mmisthisanntassystem.md), [**MmQuerySystemSize**](../wdm/nf-wdm-mmquerysystemsize.md), [**ExInitializeNPagedLookasideList**](../wdm/nf-wdm-exinitializenpagedlookasidelist.md), [**ExInitializePagedLookasideList**](../wdm/nf-wdm-exinitializepagedlookasidelist.md), [**ExInitializeResourceLite**](../wdm/nf-wdm-exinitializeresourcelite.md), [**ExReinitializeResourceLite**](../wdm/nf-wdm-exreinitializeresourcelite.md), [**ExDeleteResourceLite**](../wdm/nf-wdm-exdeleteresourcelite.md), [**ObReferenceObjectByHandle**](../wdm/nf-wdm-obreferenceobjectbyhandle.md), [**ObReferenceObjectByPointer**](../wdm/nf-wdm-obreferenceobjectbypointer.md), [**ObReferenceObject**](../wdm/nf-wdm-obreferenceobject.md), [**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md), [**RtlInitString**](../wdm/nf-wdm-rtlinitstring.md), [**RtlInitAnsiString**](../wdm/nf-wdm-rtlinitansistring.md), [**RtlInitUnicodeString**](../wdm/nf-wdm-rtlinitunicodestring.md), [**InitializeObjectAttributes**](https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes), [**ZwCreateDirectoryObject**](../wdm/nf-wdm-zwcreatedirectoryobject.md), [**ZwCreateFile**](../wdm/nf-wdm-zwcreatefile.md), [**ZwCreateKey**](../wdm/nf-wdm-zwcreatekey.md), [**ZwDeleteKey**](../wdm/nf-wdm-zwdeletekey.md), [**ZwMakeTemporaryObject**](../wdm/nf-wdm-zwmaketemporaryobject.md), [**ZwClose**](../wdm/nf-wdm-zwclose.md), [**PsGetVersion**](../wdm/nf-wdm-psgetversion.md), [**ObGetObjectSecurity**](../wdm/nf-wdm-obgetobjectsecurity.md), [**ObReleaseObjectSecurity**](../wdm/nf-wdm-obreleaseobjectsecurity.md) | 
| Initializing driver-managed internal queues. | [**KeInitializeSpinLock**](../wdm/nf-wdm-keinitializespinlock.md),[**InitializeListHead**](../wdm/nf-wdm-initializelisthead.md), [**ExInitializeSListHead**](../wdm/nf-wdm-initializeslisthead.md), [**KeInitializeDeviceQueue**](../wdm/nf-wdm-keinitializedevicequeue.md), [**IoCsqInitialize**](../wdm/nf-wdm-iocsqinitialize.md) | 




The following routines are reserved for system use. Do not use them in your driver.

- HalAcquireDisplayOwnership
- HalAllocateAdapterChannel. Use AllocateAdapterChannel instead.
- HalAllocateCrashDumpRegisters
- HalAllocateMapRegisters
- HalGetScatterGatherList. Use GetScatterGatherList instead.
- HalMakeBeep
- HalPutDmaAdapter. Use PutDmaAdapter instead.
- HalPutScatterGatherList. Use PutScatterGatherList instead.

The following obsolete routines are exported only to support existing drivers:

|Obsolete routine|Replacement |
|---|---|
|HalAllocateCommonBuffer |See [AllocateCommonBuffer](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pallocate_common_buffer) instead.|
|HalAssignSlotResources| Drivers of PnP devices are assigned resources by the PnP manager, which passes resource lists with each IRP_MN_START_DEVICE request. Drivers that must support a legacy device that cannot be enumerated by the PnP manager should use IoReportDetectedDevice and IoReportResourceForDetection.|
|HalFreeCommonBuffer |See [FreeCommonBuffer](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pfree_common_buffer) instead.|
|HalGetAdapter |See [IoGetDmaAdapter](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iogetdmaadapter) instead.|
|HalGetBusData| Instead, use [IRP_MN_QUERY_INTERFACE](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface) to query the GUID_BUS_INTERFACE_STANDARD interface. This query request returns a function pointer to GetBusData, which can be used to read from the configuration space of a given device. |
|HalGetBusDataByOffset |Instead, use IRP_MN_QUERY_INTERFACE to query the GUID_BUS_INTERFACE_STANDARD interface. This query request returns a function pointer to GetBusData, which can be used to read from the configuration space of a given device.|
|HalGetDmaAlignmentRequirement| See GetDmaAlignment instead.|
|HalGetInterruptVector| Drivers of PnP devices are assigned resources by the PnP manager, which passes resource lists with each IRP_MN_START_DEVICE request. Drivers that must support a legacy device that cannot be enumerated by the PnP manager should use IoReportDetectedDevice and IoReportResourceForDetection.|
|HalReadDmaCounter| See ReadDmaCounter instead.|
|HalSetBusData| Instead, use IRP_MN_QUERY_INTERFACE to query the GUID_BUS_INTERFACE_STANDARD interface. This query request returns a function pointer to SetBusData, which can be used to write to the configuration space of a given device. |
|HalSetBusDataByOffset| Instead, use IRP_MN_QUERY_INTERFACE to query the GUID_BUS_INTERFACE_STANDARD interface. This query request returns a function pointer to SetBusData, which can be used to write to the configuration space of a given device.| 
|HalTranslateBusAddress| The PnP manager passes lists of raw and translated resources in its IIRP_MN_START_DEVICE request for each device. Consequently, in most cases there is no need to translate bus addresses. However, if translation is required, use IRP_MN_QUERY_INTERFACE to query the GUID_BUS_INTERFACE_STANDARD interface. The query request returns a function pointer to TranslateBusAddress, which can be used to translates addresses on the parent bus to logical addresses.|
 
These obsolete routines are included in the Ntddk.h header file.

The following routine is not supported and should not be used:

- HalReturnToFirmware 

Windows performs resource balancing of PCI bus resources to open an address region for a plugged device. The rebalance operation causes the bus data for some driver's device to move dynamically (between IRP_MN_STOP_DEVICE and IRP_MN_START_DEVICE calls). Therefore, a driver must not access the bus data directly. Instead the driver must pass it down to the lower bus driver because it knows the location of the device. 

For more information, see [Stopping a Device to Rebalance Resources](https://docs.microsoft.com/windows-hardware/drivers/kernel/stopping-a-device-to-rebalance-resources). 


### Registry

Used for obtaining and reporting configuration information, and for registering interfaces in the registry.

|Function|Description|
|---|---|
|IoGetDeviceProperty|Retrieves device setup information from the registry. Use this routine, rather than accessing the registry directly, to insulate a driver from differences across platforms and from possible changes in the registry structure.|
|IoOpenDeviceInterfaceRegistryKey |Returns a handle to a registry key for storing information about a particular device interface.|
|IoOpenDeviceRegistryKey |Returns a handle to a device-specific or a driver-specific registry key for a particular device instance. |
|IoRegisterDeviceInterface |Registers device functionality (a device interface) that a driver will enable for use by applications or other system components. The I/O manager creates a registry key for the device interface. Drivers can access persistent storage under this key using IoOpenDeviceInterfaceRegistryKey.|
|IoSetDeviceInterfaceState |Enables or disables a previously registered device interface. Applications and other system components can open only interfaces that are enabled.|
|RtlCheckRegistryKey |Returns STATUS_SUCCESS if a key exists in the registry along the given relative path.|
|RtlCreateRegistryKey |Adds a key object in the registry along the given relative path.|
|RtlQueryRegistryValues |Gives a driver-supplied callback read-only access to the entries for a specified value name, along a specified relative path, in the registry, after the callback routine is given control.|
|RtlWriteRegistryValue |Writes caller-supplied data into the registry along the specified relative path at the given value name.|
|RtlDeleteRegistryValue |Removes the specified value name (and the associated value entries) from the registry along the given relative path.|
|InitializeObjectAttributes |Sets up a parameter of type OBJECT_ATTRIBUTES for a subsequent call to a ZwCreateXxx or ZwOpenXxx routine.|
|ZwCreateKey |Creates a new key in the registry with the given object's attributes, allowed access, and creation options (such as whether the key is created again when the system is booted). Alternatively, opens an existing key and returns a handle for the key object.|
|ZwOpenKey |Returns a handle for a key in the registry given the object's attributes (which must include a name for the key) and the desired access to the object.|
|ZwQueryKey |Returns information about the class of a key, and the number and sizes of its subkeys. This information includes, for example, the length of subkey names and the size of value entries.|
|ZwEnumerateKey |Returns the specified information about the subkey, as selected by a zero-based index, of an opened key in the registry.|
|ZwEnumerateValueKey |Returns the specified information about the value entry of a subkey, as selected by a zero-based index, of an opened key in the registry.|
|ZwQueryValueKey |Returns the value entry for an opened key in the registry.|
|ZwSetValueKey |Replaces (or creates) a value entry for an opened key in the registry.|
|ZwFlushKey |Forces changes made by ZwCreateKey or ZwSetValueKey for the opened key object to be written to disk.|
|ZwDeleteKey |Removes a key and its value entries from the registry as soon as the key is closed.|
|ZwClose |Releases the handle for an opened object, causing the handle to become invalid and decrementing the reference count of the object handle.|

 
### Objects and Resources

Used for setting up and freeing the objects and resources that drivers might use. 
|Function|Description|
|---|---|
|IoCreateDevice |Initializes a device object, which represents a physical, virtual, or logical device for which the driver is being loaded into the system. Then it allocates space for the driver-defined device extension associated with the device object. |
|IoDeleteDevice |Removes a device object from the system when the underlying device is removed from the system.|
|IoGetDeviceObjectPointer |Requests access to a named device object and returns a pointer to that device object if the requested access is granted. Also returns a pointer to the file object referenced by the named device object. In effect, this routine establishes a connection between the caller and the next-lower-level driver. |
|IoAttachDeviceToDeviceStack |Attaches the caller's device object to the highest device object in a chain of drivers and returns a pointer to the previously highest device object. I/O requests bound for the target device are routed first to the caller.|
|IoGetAttachedDeviceReference |Returns a pointer to the highest level device object in a driver stack and increments the reference count on that object.|
|IoDetachDevice |Releases an attachment between the caller's device object and a target driver's device object.|
|IoAllocateDriverObjectExtension |Allocates a per-driver context area with a given unique identifier.|
|IoGetDriverObjectExtension |Retrieves a previously allocated per-driver context area.|
|IoRegisterDeviceInterface |Registers device functionality (a device interface) that a driver will enable for use by applications or other system components. The I/O manager creates a registry key for the device interface. Drivers can access persistent storage under this key by calling IoOpenDeviceInterfaceRegistryKey.|
|IoIsWdmVersionAvailable |Checks whether a given WDM version is supported by the operating system.|
|IoDeleteSymbolicLink |Releases a symbolic link between a device object name and a user-visible name.|
|IoAssignArcName |Sets up a symbolic link between a named device object (such as a tape, floppy, or CD-ROM) and the corresponding ARC name for the device.|
|IoDeassignArcName |Releases the symbolic link created by calling IoAssignArcName.|
|IoSetShareAccess |Sets the access allowed to a given file object that represents a device. (Only highest-level drivers can call this routine.)|
|IoConnectInterrupt |Registers a driver's interrupt-handling routine. Drivers should use IoConnectInterruptEx instead.|
|IoDisconnectInterrupt |Unregisters an interrupt-handling routine that IoConnectInterrupt registered.|
|IoConnectInterruptEx |Registers a driver's interrupt-handling routine. Drivers can register either an InterruptService routine for line-based interrupts or an InterruptMessageService routine for message-signaled interrupts.|
|IoDisconnectInterruptEx |Unregisters an interrupt-handling routine that IoConnectInterruptEx registered.|
|IoInitializeDpcRequest |Associates a driver-supplied DpcForIsr routine with a given device object, so that the DpcForIsr routine can complete interrupt-driven I/O operations.|
|IoReadPartitionTable |Returns a list of partitions on a disk with a given sector size.|
|IoSetPartitionInformation |Sets the partition type and number for a (disk) partition.|
|IoWritePartitionTable |Writes partition tables for a disk, given the device object that represents the disk, the sector size, and a pointer to a buffer containing the drive layout structure.|
|IoCreateController |Initializes a controller object representing a physical device controller that is shared by two or more similar devices that have the same driver, and specifies the size of the controller extension.|
|IoDeleteController |Removes a controller object from the system.|
|KeInitializeSpinLock |Initializes a variable of type KSPIN_LOCK.|
|KeInitializeDpc |Initializes a DPC object, setting up a driver-supplied CustomDpc routine that can be called with a given context.|
|KeInitializeTimer |Initializes a notification timer object to the Not-Signaled state.|
|KeInitializeTimerEx |Initializes a notification or synchronization timer object to the Not-Signaled state.|
|KeInitializeEvent |Initializes an event object as a synchronization (single waiter) or notification (multiple waiters) type event and sets up its initial state (Signaled or Not-Signaled).|
|ExInitializeFastMutex |Initializes a fast mutex variable that is used to synchronize mutually exclusive access to a shared resource by a set of threads. |
|KeInitializeMutex |Initializes a mutex object as set to the Signaled state.|
|KeInitializeSemaphore |Initializes a semaphore object to a given count and specifies an upper bound for the count.|
|IoCreateNotificationEvent |Initializes a named notification event to be used to synchronize access between two or more components. Notification events are not automatically reset.|
|IoCreateSynchronizationEvent |Initializes a named synchronization event to be used to serialize access to hardware between two otherwise unrelated drivers.|
|PsCreateSystemThread |Creates a kernel-mode thread that is associated with a given process object or with the default system process. Returns a handle for the thread.|
|PsTerminateSystemThread |Terminates the current thread and satisfies as many waits as possible for the current thread object.|
|KeSetBasePriorityThread |Sets up the run-time priority, relative to the system process, for a driver-created thread.|
|KeSetPriorityThread |Sets up the run-time priority for a driver-created thread with a real-time priority attribute.|
|MmIsThisAnNtAsSystem |Returns TRUE if the current platform is a server, indicating that more resources are likely to be necessary to process I/O requests than if the machine were a client.|
|MmQuerySystemSize |Returns an estimate (small, medium, or large) of the amount of memory available on the current platform.|
|ExInitializeNPagedLookasideList |Initializes a lookaside list of nonpaged memory. After a successful initialization, fixed-size blocks can be allocated from and freed to the lookaside list.|
|ExInitializePagedLookasideList |Initializes a lookaside list of paged memory. After a successful initialization, fixed-size blocks can be allocated from and freed to the lookaside list.|
|ExInitializeResourceLite |Initializes a resource, for which the caller provides the storage, to be used for synchronization by a set of threads.|
|ExReinitializeResourceLite| Reinitializes an existing resource variable.|
|ExDeleteResourceLite |Deletes a caller-initialized resource from the system's resource list.|
|ObReferenceObjectByHandle |Returns a pointer to the object body and handle information (attributes and granted access rights), given the handle for an object, the object's type, and a mask. Specifies the desired access to the object and the preferred access mode. A successful call increments the reference count for the object.|
|ObReferenceObjectByPointer |Increments the reference count for an object so the caller can ensure that the object is not removed from the system while the caller is using it.|
|ObReferenceObject |Increments the reference count for an object, given a pointer to the object. |
|ObDereferenceObject |Releases a reference to an object (decrements the reference count), given a pointer to the object body.|
|RtlInitString |Initializes a counted string in a buffer.|
|RtlInitAnsiString |Initializes a counted ANSI string in a buffer.|
|RtlInitUnicodeString |Initializes a counted Unicode string in a buffer.|
|InitializeObjectAttributes |Initializes a parameter of type OBJECT_ATTRIBUTES for a subsequent call to a ZwCreateXxx or ZwOpenXxx routine.|
|ZwCreateDirectoryObject |Creates or opens a directory object with a specified set of object attributes and requests one or more types of access for the caller. Returns a handle for the directory object.|
|ZwCreateFile |Creates or opens a file object that represents a physical, logical, or virtual device, a directory, a data file, or a volume. Returns a handle for the file object.|
|ZwCreateKey |Creates or opens a key object in the registry and returns a handle for the key object.|
|ZwDeleteKey |Deletes an existing, open key in the registry after the last handle for the key is closed.|
|ZwMakeTemporaryObject |Resets the "permanent" attribute of an opened object, so that the object and its name can be deleted when the reference count for the object becomes zero.|
|ZwClose |Releases the handle for an opened object, causing the handle to become invalid, and decrements the reference count of the object handle.|
|PsGetVersion |Indicates whether the driver is running on a free or checked build, and optionally supplies information about the operating system version and build number. |
|ObGetObjectSecurity |Returns a buffered security descriptor for a given object. |
|ObReleaseObjectSecurity |Releases the security descriptor returned by ObGetObjectSecurity.|


### Initializing Driver-Managed Queues

Used for initializing driver-managed internal queues. 
|Function|Description|
|---|---|
|KeInitializeSpinLock |Initializes a variable of type KSPIN_LOCK. An initialized spin lock is a required parameter to the ExXxxInterlockedList routines.|
|InitializeListHead |Sets up a queue header for a driver's internal queue, given a pointer to driver-supplied storage for the queue header and queue.|
|ExInitializeSListHead |Sets up the queue header for a sequenced, interlocked, singly linked list. |
|KeInitializeDeviceQueue |Initializes a device queue object to a Not Busy state, setting up an associated spin lock for multiprocessor-safe access to device queue entries.|
|IoCsqInitialize |Initializes the dispatch table for a driver's cancel-safe IRP queue.|


## I/O Manager Routines
All kernel-mode drivers except video and SCSI miniport drivers and NDIS drivers call IoXxx routines.

References for the IoXxx routines are in alphabetical order.

For an overview of the functionality of these routines, see Summary of Kernel-Mode Support Routines.

The following routine is for system use. Do not use it in your driver.

IoUpdateDiskGeometry

## Power Management Routines

The Windows power management architecture provides a comprehensive approach to power management supported at the component (subdevice) level, in addition to the system level and the device level.

Kernel-mode drivers call the PoXxx routines to perform power management for the devices that they control. This section contains the reference pages for these routines. The PoXxx routines are declared in the Wdm.h header file.

For more information about power management, see [Power Management for Windows Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/implementing-power-management).

|Function|Description|
|---|---|
|PoCallDriver| The PoCallDriver routine passes a power IRP to the next-lower driver in the device stack. (Windows Server 2003, Windows XP, and Windows 2000 only.)
|PoClearPowerRequest| The PoClearPowerRequest routine decrements the count for the specified power request type.
|PoCreatePowerRequest| The PoCreatePowerRequest routine creates a power request object.
|PoDeletePowerRequest| The PoDeletePowerRequest routine deletes a power request object.
|PoEndDeviceBusy| The PoEndDeviceBusy routine marks the end of a period of time in which the device is busy.
|PoGetSystemWake| The PoGetSystemWake routine determines whether a specified IRP has been marked as waking the system from a sleeping state.
|PoQueryWatchdogTime| The PoQueryWatchdogTime routine indicates whether the power manager has enabled a watchdog time-out counter for any power IRP that is currently assigned to the device stack.
|PoRegisterDeviceForIdleDetection| The PoRegisterDeviceForIdleDetection routine enables or cancels idle detection and sets idle time-out values for a device.
|PoRegisterPowerSettingCallback| The PoRegisterPowerSettingCallback routine registers a power-setting callback routine to receive notifications of changes in the specified power setting.
|PoRegisterSystemState| The PoRegisterSystemState routine registers the system as busy due to certain activity.
|PoRequestPowerIrp| The PoRequestPowerIrp routine allocates a power IRP and sends it to the top driver in the device stack for the specified device.
|PoSetDeviceBusyEx| The PoSetDeviceBusyEx routine notifies the power manager that the device associated with the specified idle counter is busy.
|PoSetPowerRequest| The PoSetPowerRequest routine increments the count for the specified power request type.
|PoSetPowerState| The PoSetPowerState routine notifies the system of a change in the device power state for a device.
|PoSetSystemState| Drivers call the PoSetSystemState routine to indicate that the system is active.
|PoSetSystemWake| The PoSetSystemWake routine marks the specified IRP as one that contributed to waking the system from a sleep state.
|PoStartDeviceBusy| The PoStartDeviceBusy routine marks the start of a period of time in which the device is busy.
|PoStartNextPowerIrp| The PoStartNextPowerIrp routine signals the power manager that the driver is ready to handle the next power IRP. (Windows Server 2003, Windows XP, and Windows 2000 only.)
|PoUnregisterPowerSettingCallback| The PoUnregisterPowerSettingCallback routine unregisters a power-setting callback routine that a driver previously registered by calling the PoRegisterPowerSettingCallback routine.
|PoUnregisterSystemState| The PoUnregisterSystemState routine cancels a system state registration created by PoRegisterSystemState.
 
### Device Power Management
Starting with Windows 8, drivers can divide their device hardware into multiple logical components to enable fine-grained power management. A component has a set of power states that can be managed independently of the power states of other components in the same device. In the F0 state, the component is fully turned on. The component might support additional, low-power states F1, F2, and so on.

The power policy owner for a device is typically the device's function driver. To enable component-level power management, this driver registers the device with the power management framework (PoFx). By registering the device, the driver assumes the responsibility for informing PoFx when a component is actively being used and when the component is idle. PoFx makes intelligent idle state choices for the device based on information about the component activity, latency tolerance, expected idle durations, and wake requirements. By controlling power usage at the component level, PoFx can reduce power requirements while preserving system responsiveness. For more information, see Component-Level Power Management.

Starting with Windows 8, drivers can divide their device hardware into multiple logical components to enable fine-grained power management. A component has a set of power states that can be managed independently of the power states of other components in the same device. In the F0 state, the component is fully turned on. The component might support additional, low-power states F1, F2, and so on.

The power policy owner for a device is typically the device's function driver. To enable component-level power management, this driver registers the device with the power management framework (PoFx). By registering the device, the driver assumes the responsibility for informing PoFx when a component is actively being used and when the component is idle. PoFx makes intelligent idle state choices for the device based on information about the component activity, latency tolerance, expected idle durations, and wake requirements. By controlling power usage at the component level, PoFx can reduce power requirements while preserving system responsiveness. For more information, see Component-Level Power Management.

This section describes the routines that are implemented by the power management framework (PoFx) to enable device power management. These routines are called by the driver that is the power policy owner (PPO) for a device. Typically, the function driver for a device is the PPO for this device.

|Function|Description|
|---|---|
|PoFxActivateComponent| The PoFxActivateComponent routine increments the activation reference count on the specified component.
|PoFxCompleteDevicePowerNotRequired| The PoFxCompleteDevicePowerNotRequired routine notifies the power management framework (PoFx) that the calling driver has completed its response to a call to the driver's DevicePowerNotRequiredCallback callback routine.
|PoFxCompleteIdleCondition| The PoFxCompleteIdleCondition routine informs the power management framework (PoFx) that the specified component has completed a pending change to the idle condition.
|PoFxCompleteIdleState| The PoFxCompleteIdleState routine informs the power management framework (PoFx) that the specified component has completed a pending change to an Fx state.
|PoFxIdleComponent| The PoFxIdleComponent routine decrements the activation reference count on the specified component.
|PoFxIssueComponentPerfStateChange| The PoFxIssueComponentPerfStateChange routine submits a request to place a device component in a particular performance state. 
|PoFxIssueComponentPerfStateChangeMultiple| The PoFxIssueComponentPerfStateChangeMultiple routine submits a request to change the performance states in multiple performance state sets simultaneously for a device component. 
|PoFxNotifySurprisePowerOn| The PoFxNotifySurprisePowerOn routine notifies the power management framework (PoFx) that a device was turned on as a side effect of supplying power to some other device.
|PoFxPowerControl| The PoFxPowerControl routine sends a power control request to the power management framework (PoFx).
|PoFxQueryCurrentComponentPerfState| The PoFxQueryCurrentComponentPerfState routine retrieves the active performance state in a component's performance state set. 
|PoFxRegisterComponentPerfStates| The PoFxRegisterComponentPerfStates routine registers a device component for performance state management by the power management framework (PoFx). 
|PoFxRegisterDevice| The PoFxRegisterDevice routine registers a device with the power management framework (PoFx).
|PoFxReportDevicePoweredOn| The PoFxReportDevicePoweredOn routine notifies the power management framework (PoFx) that the device completed the requested transition to the D0 (fully on) power state.
|PoFxSetComponentLatency| The PoFxSetComponentLatency routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified component.
|PoFxSetComponentResidency| The PoFxSetComponentResidency routine sets the estimated time for how long a component is likely to remain idle after the component enters the idle condition.
|PoFxSetComponentWake| The PoFxSetComponentWake routine indicates whether the driver arms the specified component to wake whenever the component enters the idle condition.
|PoFxSetDeviceIdleTimeout| The PoFxSetDeviceIdleTimeout routine specifies the minimum time interval from when the last component of the device enters the idle condition to when the power management framework (PoFx) calls the driver's DevicePowerNotRequiredCallback routine.
|PoFxSetTargetDripsDevicePowerState| This routine is called to notify the power manager of the device's target device power state for DRIPS. The driver can override the DRIPS constraint provided by the PEP. 
|PoFxStartDevicePowerManagement| The PoFxStartDevicePowerManagement routine completes the registration of a device with the power management framework (PoFx) and starts device power management.
|PoFxUnregisterDevice| The PoFxUnregisterDevice routine removes the registration of a device from the power management framework (PoFx).
 
### Device Power Management Callbacks
Device power management callbacks are the callback routines that are required by the power management framework (PoFx) to enable device power management. The driver that is the power policy owner for the device implements these callback routines. PoFx calls these routines to query and configure the power states of the components in the device.

|Callback|Description|
|---|---|
|ComponentActiveConditionCallback| The ComponentActiveConditionCallback callback routine notifies the driver that the specified component completed a transition from the idle condition to the active condition.
|ComponentIdleConditionCallback| The ComponentIdleConditionCallback callback routine notifies the driver that the specified component completed a transition from the active condition to the idle condition.
|ComponentIdleStateCallback| The ComponentIdleStateCallback callback routine notifies the driver of a pending change to the Fx power state of the specified component.
|ComponentPerfStateCallback| The ComponentPerfStateCallback callback routine notifies the driver that its request to change the performance state of a component is complete.
|DevicePowerNotRequiredCallback| The DevicePowerNotRequiredCallback callback routine notifies the device driver that the device is not required to stay in the D0 power state.
|DevicePowerRequiredCallback| The DevicePowerRequiredCallback callback routine notifies the device driver that the device must enter and remain in the D0 power state.
|PowerControlCallback| The PowerControlCallback callback routine performs a power control operation that is requested by the power management framework (PoFx).
 
### Platform extension plug-in (PEP) reference
Platform extension plug-ins (PEPs) provide interfaces for platform power management including device power management (DPM), processor power management (PPM), and, starting with Windows 10, ACPI runtime methods. 

The types of notifications sent to platform extension plug-ins (PEPs) include:
[ACPI notifications](https://docs.microsoft.com/windows-hardware/drivers/kernel/acpi-notifications)

[Device power management (DPM) notifications](https://docs.microsoft.com/windows-hardware/drivers/kernel/dpm-notifications)

[Processor power management (PPM) notifications](https://docs.microsoft.com/windows-hardware/drivers/kernel/ppm-notifications)

[PPM power control codes](https://docs.microsoft.com/windows-hardware/drivers/kernel/ppm-power-control-codes)

|Initialization Function|Description|
|---|---|
|PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE| The PEP_ACPI_INITIALIZE_EXTENDED_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure.
|PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE| The PEP_ACPI_INITIALIZE_EXTENDED_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_EXTENDED_ADDRESS structure.
|PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE| The PEP_ACPI_INITIALIZE_GPIO_INT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure.
|PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE| The PEP_ACPI_INITIALIZE_GPIO_IO_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_GPIO_RESOURCE structure.
|PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE| The PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_INTERRUPT_RESOURCE structure.
|PEP_ACPI_INITIALIZE_IOPORT_RESOURCE| The PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure.
|PEP_ACPI_INITIALIZE_MEMORY_RESOURCE| The PEP_ACPI_INITIALIZE_MEMORY_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure.
|PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE| The PEP_ACPI_INITIALIZE_SPB_I2C_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_I2C_RESOURCE structure.
|PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE| The PEP_ACPI_INITIALIZE_SPB_SPI_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_SPI_RESOURCE structure.
|PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE| The PEP_ACPI_INITIALIZE_SPB_UART_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_SPB_UART_RESOURCE structure.
 

PEP callback routines
The callback routines are implemented by platform extension plug-ins, and are called by the Windows power management framework (PoFx).

|Callback function|Description|
|---|---|
|AcceptAcpiNotification| An AcceptAcpiNotification event callback routine handles ACPI notifications from the Windows power management framework (PoFx).
|AcceptDeviceNotification| An AcceptDeviceNotification event callback routine handles device power management (DPM) notifications from the Windows power management framework (PoFx).
|AcceptProcessorNotification| An AcceptProcessorNotification event callback routine handles processor power management (PPM) notifications from the Windows power management framework (PoFx).
|PO_ENUMERATE_INTERRUPT_SOURCE_CALLBACK| An EnumerateInterruptSource callback routine supplies a platform extension plug-in (PEP) with information about an interrupt source.
|PROCESSOR_HALT_ROUTINE| A Halt callback routine transitions the processor to an idle state.
|PowerOnDumpDeviceCallback| The PowerOnDumpDeviceCallback callback routine turns on the crash-dump device.
 
### Power management framework (PoFx) routines
Some miscellaneous PoFx routines and structures will most likely end up in the power-management section of the Kernel-Mode Driver Architecture doc set.

|Initialization Function|Description|
|---|---|
|PoFxRegisterPlugin| The PoFxRegisterPlugin routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx).
|PoFxRegisterPluginEx| The PoFxRegisterPluginEx routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx).
|PoFxRegisterCoreDevice| The PoFxRegisterCoreDevice routine registers a new core system resource with the Windows power management framework (PoFx).
|PoFxRegisterCrashdumpDevice| The PoFxRegisterCrashdumpDevice routine registers a crash-dump device.
|PoFxPowerOnCrashdumpDevice| The PoFxPowerOnCrashdumpDevice routine requests that a crash-dump device be turned on.

|Callback function|Description|
|---|---|
|POFXCALLBACKENUMERATEUNMASKEDINTERRUPTS| The EnumerateUnmaskedInterrupts routine enumerates interrupt sources whose interrupts are unmasked and enabled.
|POFXCALLBACKPLATFORMIDLEVETO| The PlatformIdleVeto routine increments or decrements the veto count for a veto code for a platform idle state.
|POFXCALLBACKPROCESSORHALT| The ProcessorHalt routine prepares the processor to be halted.
|POFXCALLBACKPROCESSORIDLEVETO| The ProcessorIdleVeto routine increments or decrements the veto count for a veto code for a processor idle state.
|POFXCALLBACKREQUESTCOMMON| The RequestCommon routine is a generic request handler.
|POFXCALLBACKREQUESTINTERRUPT| The RequestInterrupt routine requests that the operating system replay an edge-triggered interrupt that might have been lost while the hardware platform was in a low-power state.
|POFXCALLBACKREQUESTWORKER| The RequestWorker routine is called by a platform extension plug-in (PEP) to inform the Windows power management framework (PoFx) that the platform extension plug-in (PEP) has a work request to submit on behalf of the specified device.
|POFXCALLBACKCRITICALRESOURCE| The TransitionCriticalResource routine changes the active/inactive state of a core system component.
|POFXCALLBACKUPDATEPLATFORMIDLESTATE| The UpdatePlatformIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified platform idle state.
|POFXCALLBACKUPDATEPROCESSORIDLESTATE| The UpdateProcessorIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified processor idle state.
|ComponentCriticalTransitionCallback| The ComponentCriticalTransitionCallback callback routine handles a transition of the specified component between the F0 (fully on) and low-power Fx component power states.
 

## Configuration Manager Routines
The configuration manager routines use the CmXxx naming convention.

- CmCallbackGetKeyObjectID
- CmCallbackGetKeyObjectIDEx
- CmCallbackReleaseKeyObjectIDEx
- CmGetBoundTransaction
- CmGetCallbackVersion
- CmRegisterCallback
- CmRegisterCallbackEx
- CmSetCallbackObjectContext
- CmUnRegisterCallback

## Kernel Transaction Manager (KTM) Routines
This section describes the routines, structures, and enumerations that the Kernel Transaction Manager (KTM) provides.

### Transaction Manager Object Routines
This section includes the following topics:

- TmRecoverTransactionManager
- ZwCreateTransactionManager
- ZwOpenTransactionManager
- ZwQueryInformationTransactionManager
- ZwRecoverTransactionManager
- ZwRollforwardTransactionManager

### Transaction Object Routines
This section includes the following topics:

- TmCommitTransaction
- TmGetTransactionId
- TmIsTransactionActive
- TmRollbackTransaction
- ZwCommitTransaction
- ZwCreateTransaction
- ZwEnumerateTransactionObject
- ZwOpenTransaction
- ZwQueryInformationTransaction
- ZwRollbackTransaction
- ZwSetInformationTransaction

###  Enlistment Object Routines
This section includes the following topics:

- TmCommitComplete
- TmCommitEnlistment
- TmCreateEnlistment
- TmDereferenceEnlistmentKey
- TmPrepareComplete
- TmPrePrepareComplete
- TmPrepareEnlistment
- TmPrePrepareEnlistment
- TmReadOnlyEnlistment
- TmRecoverEnlistment
- TmReferenceEnlistmentKey
- TmRequestOutcomeEnlistment
- TmRollbackComplete
- TmRollbackEnlistment
- TmSinglePhaseReject
- ZwCommitComplete
- ZwCommitEnlistment
- ZwCreateEnlistment
- ZwOpenEnlistment
- ZwPrepareComplete
- ZwPrePrepareComplete
- ZwPrepareEnlistment
- ZwPrePrepareEnlistment
- ZwQueryInformationEnlistment
- ZwReadOnlyEnlistment
- ZwRecoverEnlistment
- ZwRollbackComplete
- ZwRollbackEnlistment
- ZwSetInformationEnlistment
- ZwSinglePhaseReject

### Resource Manager Object Routines
This section includes the following topics:

- ResourceManagerNotification
- TmEnableCallbacks
- TmRecoverResourceManager
- ZwCreateResourceManager
- ZwGetNotificationResourceManager
- ZwOpenResourceManager
- ZwQueryInformationResourceManager
- ZwRecoverResourceManager
- ZwSetInformationResourceManager

## Security Reference Monitor Routines
Generally, higher-level drivers, particularly network drivers, call these routines.

References for the SeXxx routines are in alphabetical order.

- SeAccessCheck
- SeAssignSecurity
- SeAssignSecurityEx
- SeDeassignSecurity
- SeFreePrivileges
- - SeSinglePrivilegeCheck
SeValidSecurityDescriptor


## Core Kernel Library Support Routines
All kernel-mode drivers except video and SCSI miniport drivers and NDIS drivers are likely to call at least some KeXxx routines.

This section describes references for the KeXxx routines, in alphabetical order.

For an overview of the functionality of these routines, see Summary of Kernel-Mode Support Routines.

The following routines are reserved for system use:

- KeAcquireSpinLockRaiseToSynch
- KeBreakinBreakpoint
- KeEnterKernelDebugger
- KeFlushWriteBuffer
- KeGetBugMessageText
- KeRaiseIrqlToSynchLevel
- KeRemoveByKeyDeviceQueueIfBusy
- KeSetTimeUpdateNotifyRoutine

## Executive Library Support Routines
This section describes the executive library support routines. These routines use the ExXxx naming convention and are listed in alphabetical order.

The following executive support routines are reserved for system use. Do not use them in your driver.

|Routine|Replacement|
|---|---|
|ExAcquireSpinLock| Use KeAcquireSpinLock instead.|
|ExAcquireSpinLockAtDpcLevel| Use KeAcquireSpinLockAtDpcLevel instead.|
|ExfInterlockedDecrementLong| Use InterlockedDecrement instead.|
|ExfInterlockedExchangeUlong| Use InterlockedExchange instead.|
|ExfInterlockedIncrementLong| Use InterlockedIncrement instead.|
|ExfInterlockedPopEntryList| Use ExInterlockedPopEntryList instead.|
|ExfInterlockedPushEntryList| Use ExInterlockedPushEntryList instead.|
|ExReleaseSpinLock| Use KeReleaseSpinLock instead.|
|ExReleaseSpinLockFromDpcLevel| Use KeReleaseSpinLockFromDpcLevel instead.|
|ExVerifySuite||


## CLFS Library Routines
This section contains reference pages for routines implemented by the Common Log File System (CLFS). For a listing of the CLFS management routines, see CLFS Management Library Routines. For a conceptual discussion of CLFS, see Common Log File System in the design guide section of this documentation. For definitions of key terms used in the CLFS documentation, see CLFS Terminology. 

|Callback function|Description|
|---|---|
|ClfsAddLogContainer| The ClfsAddLogContainer routine adds a container to a CLFS log.
|ClfsAddLogContainerSet| The ClfsAddLogContainerSet routine atomically adds a set of containers to a CLFS log.
|ClfsAdvanceLogBase| The ClfsAdvanceLogBase routine sets the base LSN of a CLFS stream.
|ClfsAlignReservedLog| The ClfsAlignReservedLog routine calculates the size of the space that must be reserved for a specified set of records. The size calculation includes the space required for headers and the space required for sector alignment.
|ClfsAllocReservedLog| The ClfsAllocReservedLog routine reserves space in a marshalling area for a set of records.
|ClfsCloseAndResetLogFile| The ClfsCloseAndResetLogFile routine releases all references to a specified log file object and marks its associated stream for reset.
|ClfsCloseLogFileObject| The ClfsCloseLogFileObject routine releases all references to a log file object.
|ClfsCreateLogFile| The ClfsCreateLogFile routine creates or opens a CLFS stream. If necessary, ClfsCreateLogFile also creates the underlying physical log that holds the stream's records.
|ClfsCreateMarshallingArea| The ClfsCreateMarshallingArea routine creates a marshalling area for a CLFS stream and returns a pointer to an opaque context that represents the new marshalling area.
|ClfsCreateScanContext| The ClfsCreateScanContext routine creates a scan context that can be used to iterate over the containers of a specified CLFS log.
|ClfsDeleteLogByPointer| The ClfsDeleteLogByPointer routine marks a CLFS stream for deletion. 
|ClfsDeleteLogFile| The ClfsDeleteLogFile routine marks a CLFS stream for deletion.
|ClfsDeleteMarshallingArea| The ClfsDeleteMarshallingArea routine deletes a marshalling area.
|ClfsFlushBuffers| The ClfsFlushBuffers routine forces all log I/O blocks in a specified marshalling area to stable storage.
|ClfsFlushToLsn| The ClfsFlushToLsn routine forces, to stable storage, all records that have an LSN less than or equal to a specified LSN.
|ClfsGetContainerName| The ClfsGetContainerName routine returns the path name of a specified container.
|ClfsGetIoStatistics| The ClfsGetIoStatistics routine returns I/O statistics for a specified CLFS log.
|ClfsLsnBlockOffset| The ClfsLsnBlockOffset routine returns the sector-aligned block offset contained in a specified LSN.
|ClfsLsnContainer| The ClfsLsnContainer routine returns the logical container identifier contained in a specified LSN.
|ClfsLsnCreate| The ClfsLsnCreate routine creates a log sequence number (LSN), given a container identifier, a block offset, and a record sequence number.
|ClfsLsnEqual| The ClfsLsnEqual routine determines whether two LSNs from the same stream are equal.
|ClfsLsnGreater| The ClfsLsnGreater routine determines whether one LSN is greater than another LSN. The two LSNs must be from the same stream.
|ClfsLsnLess| The ClfsLsnLess routine determines whether one LSN is less than another LSN. The two LSNs must be from the same stream. 
|ClfsLsnNull| The ClfsLsnNull routine determines whether a specified LSN is equal to the smallest possible LSN, CLFS_LSN_NULL.
|ClfsLsnRecordSequence| The ClfsLsnRecordSequence routine returns the record sequence number contained in a specified LSN.
|ClfsQueryLogFileInformation| The ClfsQueryLogFileInformation routine returns metadata and state information for a specified CLFS stream or its underlying physical log or both.
|ClfsReadLogRecord| The ClfsReadLogRecord routine reads a target record in a CLFS stream and returns a read context that the caller can use to read the records preceding or following it in the stream.
|ClfsReadNextLogRecord| The ClfsReadNextLogRecord routine reads the next record in a sequence, relative to the current record in a read context.
|ClfsReadPreviousRestartArea| The ClfsReadPreviousRestartArea routine reads the previous restart record relative to the current record in a read context.
|ClfsReadRestartArea| The ClfsReadRestartArea routine reads the restart record that was most recently written to a specified CLFS stream.
|ClfsRemoveLogContainer| The ClfsRemoveLogContainer routine removes a container from a CLFS log.
|ClfsRemoveLogContainerSet| The ClfsRemoveLogContainerSet routine atomically removes a set of containers from a CLFS log.
|ClfsReserveAndAppendLog| The ClfsReserveAndAppendLog routine reserves space in a marshalling area or appends a record to a marshalling area or does both atomically.
|ClfsReserveAndAppendLogAligned| The ClfsReserveAndAppendLogAligned routine reserves space in a marshalling area or appends a record to a marshalling area or does both atomically. The record's data is aligned on specified boundaries.
|ClfsScanLogContainers| The ClfsScanLogContainers routine retrieves descriptive information for a sequence of containers that belong to a particular CLFS log.
|ClfsSetArchiveTail| The ClfsSetArchiveTail routine sets the archive tail of a CLFS log to a specified LSN.
|ClfsSetEndOfLog| The ClfsSetEndOfLog routine truncates a CLFS stream.
|ClfsSetLogFileInformation| The ClfsSetLogFileInformation routine sets metadata and state information for a specified stream and its underlying physical log.
|ClfsTerminateReadLog| The ClfsTerminateReadLog routine invalidates a specified read context after freeing resources associated with the context.
|ClfsWriteRestartArea| The ClfsWriteRestartArea routine atomically appends a new restart record to a CLFS stream, flushes the restart record to stable storage, and optionally updates the base LSN of the stream.
 


## IRPs

Microsoft Windows use I/O Request Packets (IRPs) to send messages to device drivers. An IRP is a data structure that contains specific information used to convey the status of an event. For more information about the IRP data structure, see IRP and [IRP Major Function Codes](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-major-function-codes).

Your driver can use System-Supplied Driver Interfaces to send IRPs to other drivers. 

In addition to the Standard IRP Codes, there are three additional types of IRPs for specific technologies:

-   Plug and Play IRPs, see [Plug and Play Minor IRPs](https://docs.microsoft.com/windows-hardware/drivers/kernel/plug-and-play-minor-irps)
-   Power Management IRPs, see [Power Management Minor IRPs](https://docs.microsoft.com/windows-hardware/drivers/kernel/power-management-minor-irps)
-   Windows Management Instrumentation (WMI) IRPs, see [WMI Minor IRPs](https://docs.microsoft.com/windows-hardware/drivers/kernel/wmi-minor-irps)

This section describes kernel-mode support routines that drivers can call:

-   While processing IRPs. 

-   To allocate and set up IRPs for requests from higher-level drivers to lower drivers.

-   To use file objects.

### Processing IRPs

|Function|Description|
|---|---|
|IoGetCurrentIrpStackLocation |Returns a pointer to the caller's I/O stack location in a given IRP.|
|IoGetNextIrpStackLocation |Returns a pointer to the next-lower-level driver's I/O stack location in a given IRP.|
|IoCopyCurrentIrpStackLocationToNext Copies the IRP stack parameters from the current stack location to the stack location of the next-lower driver and allows the current driver to set an I/O completion routine.|
|IoSkipCurrentIrpStackLocation |Copies the IRP stack parameters from the current stack location to the stack location of the next-lower driver and does not allow the current driver to set an I/O completion routine.|
|IoGetRelatedDeviceObject |Returns a pointer to the device object represented by a given file object.|
|IoGetFunctionCodeFromCtlCode |Returns the value of the function field within a given IOCTL_XXX or FSCTL_XXX code.|
|IoValidateDeviceIoControlAccess|Verifies that the sender of an IRP_MJ_DEVICE_CONTROL or IRP_MJ_FILE_SYSTEM_CONTROL IRP has the access specified.|
|IoSetCompletionRoutine |Registers a driver-supplied IoCompletion routine for an IRP, so the IoCompletion routine is called when the next-lower-level driver has completed the requested operation in one or more of the following ways: successfully, with an error, or by canceling the IRP.|
|IoSetCompletionRoutineEx |Same as IoSetCompletionRoutine, except that it guarantees a non-Plug and Play driver is not unloaded before the IoCompletion routine exits.|
|IoCallDriver |Sends an IRP to a lower-level driver.|
|PoCallDriver |Sends an IRP with major function code IRP_MJ_POWER to the next-lower driver.|
|IoForwardIrpSynchronously |Sends an IRP to a lower-level driver synchronously.|
|IoMarkIrpPending |Marks a given IRP indicating that STATUS_PENDING was returned because further processing is required by another driver routine or by a lower-level driver.|
|IoStartPacket |Calls the driver's StartIo routine with the given IRP for the given device object or inserts the IRP into the device queue if the device is already busy, specifying whether the IRP is cancelable.|
|IoSetStartIoAttributes |Sets attributes for when the driver's StartIo routine will execute.|
|IoAcquireCancelSpinLock |Synchronizes cancelable state transitions for IRPs in a multiprocessor-safe manner.|
|IoSetCancelRoutine |Sets or clears the Cancel routine in an IRP. Setting a Cancel routine makes an IRP cancelable.|
|IoReleaseCancelSpinLock |Releases the cancel spin lock when the driver has changed the cancelable state of an IRP or releases the cancel spin lock from the driver's Cancel routine.|
|IoCancelIrp |Marks an IRP as canceled.|
|IoReadPartitionTable |Returns a list of partitions on a disk with a given sector size.|
|IoSetPartitionInformation |Sets the partition type and number for a (disk) partition.|
|IoWritePartitionTable |Writes partition tables for a disk, given the device object representing the disk, the sector size, and a pointer to a buffer containing the drive geometry.|
|IoAllocateErrorLogEntry |Allocates and initializes an error log packet; returns a pointer so that the caller can supply error-log data and call IoWriteErrorLogEntry with the packet.|
|IoWriteErrorLogEntry |Queues a previously allocated and filled-in error log packet to the system error logging thread.|
|IoIsErrorUserInduced |Returns a Boolean value indicating whether an I/O request failed due to one of the following conditions: STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_UNRECOGNIZED_MEDIA, STATUS_VERIFY_REQUIRED, STATUS_WRONG_VOLUME, STATUS_MEDIA_WRITE_PROTECTED, or STATUS_NO_MEDIA_IN_DEVICE. If the result is TRUE, a removable-media driver must call IoSetHardErrorOrVerifyDevice before completing the IRP.|
|IoSetHardErrorOrVerifyDevice |Supplies the device object for which the given IRP was failed due to a user-induced error, such as supplying the incorrect media for the requested operation or changing the media before the requested operation was completed. A file system driver uses the associated device object to notify the user, who can then correct the error or retry the operation.|
|IoRaiseHardError |Notifies the user that the given IRP was failed on the given device object for an optional VPB, so that the user can correct the error or retry the operation.|
|IoRaiseInformationalHardError |Notifies the user of an error, providing an I/O error status and an optional string supplying more information.|
|ExRaiseStatus |Raises an error status and causes a caller-supplied structured exception handler to be called. Useful only to highest-level drivers that supply exception handlers, in particular to file systems.|
|IoStartNextPacket |Dequeues the next IRP for a given device object, specifies whether the IRP is cancelable, and calls the driver's StartIo routine.|
|IoStartNextPacketByKey |Dequeues the next IRP for a device object according to a specified sort-key value, specifies whether the IRP is cancelable, and calls the driver's StartIo routine.|
|IoCompleteRequest |Completes an I/O request, giving a priority boost to the original caller and returning a given IRP to the I/O system for disposal: either to call any IoCompletion routines supplied by higher-level drivers, or to return status to the original requester of the operation.|
|IoGetCurrentProcess |Returns a pointer to the current process. Useful only to highest-level drivers.|
|IoGetInitialStack |Returns the initial base address of the current thread's stack. Useful only to highest-level drivers.|
|IoGetRemainingStackSize |Returns the amount of available stack space. Useful only to highest-level drivers.|
|IoGetStackLimits |Returns the boundaries of the current thread's stack frame. Useful only to highest-level drivers.|
|IoCsqInitialize |Initializes the dispatch table for a driver's cancel-safe IRP queue.|
|IoCsqInsertIrp |Inserts an IRP into a driver's cancel-safe IRP queue.|
|IoCsqRemoveIrp |Removes the specified IRP from a driver's cancel-safe IRP queue.|
|IoCsqRemoveNextIrp |Removes the next IRP from a driver's cancel-safe IRP queue. |

 ### Driver-Allocated IRPs
|Function|Description|
|---|---|
|oBuildAsynchronousFsdRequest |Allocates and sets up an IRP that specifies a major function code (IRP_MJ_PNP, IRP_MJ_READ, IRP_MJ_WRITE, IRP_MJ_SHUTDOWN, or IRP_MJ_FLUSH_BUFFERS) with a pointer to: The lower driver's device object on which the I/O should occur. A buffer that will contain the data to be read or that contains the data to be written. The length of the buffer in bytes. The starting offset on the media. The I/O status block where the called driver can return status information and the caller's IoCompletion routine can access it.  Returns a pointer to the IRP so the caller can set any necessary minor function code and set up its IoCompletion routine before sending the IRP to the target driver.
|IoBuildSynchronousFsdRequest |Allocates and sets up an IRP specifying a major function code (IRP_MJ_PNP, IRP_MJ_READ, IRP_MJ_WRITE, IRP_MJ_SHUTDOWN, or IRP_MJ_FLUSH_BUFFERS) with a pointer to: The lower driver's device object on which the I/O should occur. A buffer that will contain the data to be read or that contains the data to be written. The length of the buffer in bytes.  The starting offset on the media.  An event object to be set to the Signaled state when the requested operation completes.  The I/O status block where the called driver can return status information and the caller's IoCompletion routine can access it. Returns a pointer to the IRP so the caller can set any necessary minor function code and set up its IoCompletion routine before sending the IRP to the target driver.
|IoBuildDeviceIoControlRequest |Allocates and sets up an IRP specifying a major function code (either IRP_MJ_INTERNAL_DEVICE_CONTROL or IRP_MJ_DEVICE_CONTROL) with an optional input or output buffer; a pointer to the lower driver's device object; an event to be set to the Signaled state when the requested operation completes; and an I/O status block to be set by the driver that receives the IRP. Returns a pointer to the IRP so the caller can set the appropriate IOCTL_XXX before sending the IRP to the next-lower-level driver.
|PoRequestPowerIrp |Allocates and initializes an IRP with major function code IRP_MJ_POWER and then sends the IRP to the top-level driver in the device stack for the specified device object.
|IoSizeOfIrp |Returns the size in bytes required for an IRP with a given count of I/O stack locations.
|IoAllocateIrp |Allocates an IRP, given the number of I/O stack locations (optionally, for the caller, but at least one for each driver layered under the caller) and whether to charge quota against the caller. Returns a pointer to an IRP in nonpaged system space if successful; otherwise, returns NULL.
|IoInitializeIrp |Initializes an IRP, given a pointer to an already allocated IRP, its length in bytes, and its number of I/O stack locations.
|IoSetNextIrpStackLocation |Sets the current IRP stack location to the caller's location in an IRP. The stack location must have been allocated by a preceding call to IoAllocateIrp that specified a stack-size argument large enough to give the caller its own stack location.
|IoAllocateMdl |Allocates an MDL large enough to map the starting address and length supplied by the caller; optionally associates the MDL with a given IRP.
|IoBuildPartialMdl |Builds an MDL for the specified starting virtual address and length in bytes from a given source MDL. Drivers that split large transfer requests into a number of smaller transfers can call this routine.
|IoFreeMdl |Releases a given MDL allocated by the caller.
|IoMakeAssociatedIrp |Allocates and initializes an IRP to be associated with a master IRP sent to the highest-level driver, allowing the driver to "split" the original request and send associated IRPs on to lower-level drivers or to the device.
|IoSetCompletionRoutine |Registers a driver-supplied IoCompletion routine with a given IRP, so that the IoCompletion routine is called when lower-level drivers have completed the request. The IoCompletion routine lets the caller release the IRP it allocated with IoAllocateIrp or IoBuildAsynchronousFsdRequest; to release any other resources it allocated to set up an IRP for lower drivers; and to perform any I/O completion processing necessary.
|IoSetCompletionRoutineEx |Same as IoSetCompletionRoutine, except that it guarantees a non-Plug and Play driver is not unloaded before the IoCompletion routine exits.
|IoCallDriver |Sends an IRP to a lower-level driver.
|IoFreeIrp |Releases an IRP that was allocated by the caller.
|IoReuseIrp |Reinitializes for reuse an IRP that was previously allocated by IoAllocateIrp.


### File Objects
|Function|Description|
|---|---|
|nitializeObjectAttributes |Initializes a parameter of type OBJECT_ATTRIBUTES for a subsequent call to a ZwCreateXxx or ZwOpenXxx routine.|
|ZwCreateFile |Creates or opens a file object representing a physical, logical, or virtual device, a directory, a data file, or a volume.|
|ZwQueryInformationFile |Returns information about the state or attributes of an open file.|
|IoGetFileObjectGenericMapping |Returns information about the mapping between generic access rights and specific access rights for file objects.|
|ZwReadFile |Returns data from an open file.|
|ZwSetInformationFile |Changes information about the state or attributes of an open file.|
|ZwWriteFile |Transfers data to an open file.|
|ZwClose |Releases the handle for an opened object, causing the handle to become invalid and decrementing the reference count of the object handle.|


## Silo DDIs

This section describes the silo DDIs. These DDIs offer the ability for kernel components to learn about the server silos that are created and destroyed on a machine.  Components register to receive notifications for these events and optionally store state that is associated with each silo.


### Context management
These DDIs provide the ability to assign and retrieve context structures on silo objects. This allows drivers to attach per-silo information for each silo.

- PsAllocSiloContextSlot 
- PsFreeSiloContextSlot 
- PsCreateSiloContext 
- PsInsertSiloContext 
- PsReplaceSiloContext 
- PsInsertPermanentSiloContext 
- PsGetPermanentSiloContext 
- PsMakeSiloContextPermanent 
- PsGetSiloContext 
- PsRemoveSiloContext 
- PsReferenceSiloContext 
- PsDereferenceSiloContext 
- SILO_CONTEXT_CLEANUP_CALLBACK 


### Threading
These DDIs provide the ability to set and retrieve the silo for the current thread.

- PsAttachSiloToCurrentThread 
- PsDetachSiloFromCurrentThread 
- PsGetCurrentSilo 
- PsGetCurrentServerSilo 

### Monitoring
These DDIs provide the ability for a driver to receive notifications about silo creation and termination events.

- PsRegisterSiloMonitor 
- PsUnregisterSiloMonitor 
- PsStartSiloMonitor 
- PsGetSiloMonitorContextSlot 
- SILO_MONITOR_CREATE_CALLBACK 
- SILO_MONITOR_TERMINATE_CALLBACK 

### Helpers
These DDIs are helpful for working with silo objects.

- PsGetJobSilo 
- PsGetJobServerSilo 
- PsGetEffectiveServerSilo 
- PsIsHostSilo 
- PsGetHostSilo 
- PsTerminateServerSilo 


## Synchronization
This section describes the kernel-mode support routines that drivers can call to:

-   Synchronize the execution of their own standard driver routines (Driver Routines and I/O Objects). 
-   Temporarily change the current IRQL for a call to a support routine or that return the current IRQL (IRQL). 
-   Synchronize access to resources with spin locks or to perform interlocked operations without spin locks (Spin Locks and Interlocks). 
-   Manage time-outs or determine system time (Timers). 
-   Use system threads or to manage synchronization within a nonarbitrary thread context (Driver Threads, Dispatcher Objects, and Resources). 

### Driver Routines and I/O Objects
|Function|Description|
|---|---|
|KeSynchronizeExecution |Synchronizes the execution of a driver-supplied SynchCritSection routine with that of the ISR associated with a set of interrupt objects, given a pointer to the interrupt objects.
|IoRequestDpc |Queues a driver-supplied DpcForIsr routine to complete interrupt-driven I/O processing at a lower IRQL.
|KeInsertQueueDpc |Queues a DPC to be executed as soon as the IRQL of a processor drops below DISPATCH_LEVEL; returns FALSE if the DPC object is already queued.
|KeRemoveQueueDpc |Removes a given DPC object from the DPC queue; returns FALSE if the object is not in the queue.
|KeSetImportanceDpc |Controls how a particular DPC is queued and, to some degree, how soon the DPC routine is run.
|KeSetTargetProcessorDpc |Controls on which processor a particular DPC subsequently will be queued.
|KeFlushQueuedDpcs |Call this routine to wait for all queued DPCs to execute.
|AllocateAdapterChannel |Connects a device object to an adapter object and calls a driver-supplied AdapterControl routine to carry out an I/O operation through the system DMA controller or a bus-master adapter as soon as the appropriate DMA channel and any necessary map registers are available. (This routine reserves exclusive access to a DMA channel and map registers for the specified device.)
|FreeAdapterChannel |Releases an adapter object, representing a system DMA channel, and optionally releases map registers, if any were allocated.
|FreeMapRegisters |Releases a set of map registers that were saved from a call to AllocateAdapterChannel, after the registers have been used by IoMapTransfer and the bus-master DMA transfer is complete.
|IoAllocateController |Connects a device object to a controller object and calls a driver-supplied ControllerControl routine to carry out an I/O operation on the device controller as soon as the controller is not busy. (This routine reserves exclusive access to the hardware controller for the specified device.)
|IoFreeController |Releases a controller object, provided that all device operations queued to the controller for the current IRP have completed.
|IoStartTimer |Enables the timer for a given device object and calls the driver-supplied IoTimer routine once per second thereafter.
|IoStopTimer |Disables the timer for a given device object so that the driver-supplied IoTimer routine is not called unless the driver reenables the timer.
|KeSetTimer |Sets the absolute or relative interval at which a timer object will be set to the Signaled state and optionally supplies a timer DPC to be executed after the interval expires.
|KeSetTimerEx |Sets the absolute or relative interval at which a timer object will be set to the Signaled state, optionally supplies a timer DPC to be executed when the interval expires, and optionally supplies a recurring interval for the timer.
|KeCancelTimer |Cancels a timer object before the interval passed to KeSetTimer expires; dequeues a timer DPC before the timer interval, if any was set, expires.
|KeReadStateTimer |Returns whether a given timer object is set to the Signaled state.
|IoStartPacket |Calls the driver's StartIo routine with the given IRP for the given device object or inserts the IRP into the device queue if the device is already busy, specifying whether the IRP is cancelable.
|IoStartNextPacket |Dequeues the next IRP for a given device object, specifying whether the IRP is cancelable, and calls the driver's StartIo routine.
|IoStartNextPacketByKey |Dequeues the next IRP, according to the specified sort-key value, for a given device object. Specifies whether the IRP is cancelable and calls the driver's StartIo routine.
|IoSetCompletionRoutine |Registers a driver-supplied IoCompletion routine with a given IRP, so the IoCompletion routine is called when the next-lower-level driver has completed the requested operation in one or more of the following ways: successfully, with an error, or by canceling the IRP.
|IoSetCompletionRoutineEx |Same as IoSetCompletionRoutine, except that it guarantees a non-Plug and Play driver is not unloaded before the IoCompletion routine exits.
|IoSetCancelRoutine |Sets or clears the Cancel routine in an IRP. Setting a Cancel routine makes an IRP cancelable.
|KeStallExecutionProcessor |Stalls the caller (a device driver) for a given interval on the current processor.
|ExAcquireResourceExclusiveLite |Acquires an initialized resource for exclusive access by the calling thread and optionally waits for the resource to be acquired.
|ExAcquireResourceSharedLite |Acquires an initialized resource for shared access by the calling thread and optionally waits for the resource to be acquired. 
|ExAcquireSharedStarveExclusive |Acquires a given resource for shared access without waiting for any pending attempts to acquire exclusive access to the same resource.
|ExAcquireSharedWaitForExclusive |Acquires a given resource for shared access, optionally waiting for any pending exclusive waiters to acquire and release the resource first. 
|ExReleaseResourceForThreadLite |Releases a given resource that was acquired by the given thread. 
|ZwReadFile |Reads data from an open file. If the caller opened the file object with certain parameters, the caller can wait for the file handle to be returned for completion of the I/O.
|ZwWriteFile |Writes data to an open file. If the caller opened the file object with certain parameters, the caller can wait for the file handle to be returned for completion of the I/O.


### IRQL
|Function|Description|
|---|---|
|KeRaiseIrql |Raises the hardware priority to a given IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor.
|KeRaiseIrqlToDpcLevel |aises the hardware priority to IRQL DISPATCH_LEVEL, thereby masking off interrupts of equivalent or lower IRQL on the current processor. 
|KeLowerIrql |Restores the IRQL on the current processor to its original value.
|KeGetCurrentIrql |Returns the current hardware priority IRQL value.

### Spin Locks and Interlocks
|Function|Description|
|---|---|
|oAcquireCancelSpinLock |Synchronizes cancelable state transitions for IRPs in a multiprocessor-safe manner.
|IoSetCancelRoutine |Sets or clears the Cancel routine in an IRP during a cancelable state transition. Setting a Cancel routine makes an IRP cancelable.
|IoReleaseCancelSpinLock |Releases the cancel spin lock when the driver has changed the cancelable state of an IRP or releases the cancel spin lock from the driver's Cancel routine.
|KeInitializeSpinLock |Initializes a variable of type KSPIN_LOCK, used to synchronize access to data shared among non-ISR routines. An initialized spin lock also is a required parameter to the ExInterlockedXxx routines.
|KeAcquireSpinLock |Acquires a spin lock so the caller can synchronize access to shared data safely on multiprocessor platforms. 
|KeAcquireSpinLockRaiseToDpc |Acquires a spin lock so the caller can synchronize access to shared data safely on multiprocessor platforms.
|KeReleaseSpinLock |Releases a spin lock that was acquired by calling KeAcquireSpinLock and restores the original IRQL at which the caller was running.
|KeAcquireSpinLockAtDpcLevel |Acquires a spin lock, provided that the caller is already running at IRQL DISPATCH_LEVEL.
|KeTryToAcquireSpinLockAtDpcLevel |Acquires a spin lock that is not already held, provided that the caller is already running at IRQL DISPATCH_LEVEL.
|KeReleaseSpinLockFromDpcLevel |Releases a spin lock that was acquired by calling KeAcquireSpinLockAtDpcLevel.
|KeAcquireInStackQueuedSpinLock |Acquires a queued spin lock so the caller can synchronize access to shared data safely on multiprocessor platforms. 
|KeReleaseInStackQueuedSpinLock |Releases a queued spin lock that was acquired by calling KeAcquireInStackQueuedSpinLock.
|KeAcquireInStackQueuedSpinLockAtDpcLevel |Acquires a queued spin lock, provided that the caller is already running at IRQL DISPATCH_LEVEL.
|KeReleaseInStackQueuedSpinLockFromDpcLevel |Releases a queued spin lock that was acquired by calling KeAcquireInStackQueuedSpinLockAtDpcLevel.
|KeAcquireInterruptSpinLock |Acquires the spin lock that synchronizes access with an interrupt's ISR.
|KeReleaseInterruptSpinLock |Release the spin lock that synchronized access with an interrupt's ISR.
|ExInterlockedXxxList |Insert and remove IRPs in a driver-managed internal queue, which is protected by an initialized spin lock for which the driver provides the storage.
|KeXxxDeviceQueue |Insert and remove IRPs in a driver-allocated and managed internal device queue object, which is protected by a built-in spin lock.
|ExInterlockedAddUlong |Adds a value to a variable of type ULONG as an atomic operation, using a spin lock to ensure multiprocessor-safe access to the variable; returns the value of the variable before the call occurred.
|ExInterlockedAddLargeInteger |Adds a value to a variable of type LARGE_INTEGER as an atomic operation, using a spin lock to ensure multiprocessor-safe access to the variable; returns the value of the variable before the call occurred.
|InterlockedIncrement |Increments a variable of type LONG as an atomic operation. The sign of the return value is the sign of the result of the operation.
|InterlockedDecrement |Decrements a variable of type LONG as an atomic operation. The sign of the return value is the sign of the result of the operation. 
|InterlockedExchange |Sets a variable of type LONG to a specified value as an atomic operation; returns the value of the variable before the call occurred.
|InterlockedExchangeAdd |Adds a value to a given integer variable as an atomic operation; returns the value of the variable before the call occurred.
|InterlockedCompareExchange |Compares the values referenced by two pointers. If the values are equal, resets one of the values to a caller-supplied value in an atomic operation. 
|InterlockedCompareExchangePointer |Compares the pointers referenced by two pointers. If the pointer values are equal, resets one of the values to a caller-supplied value in an atomic operation.
|ExInterlockedCompareExchange64 |Compares one integer variable to another and, if they are equal, resets the first variable to a caller-supplied ULONGLONG-type value as an atomic operation. 
|KeGetCurrentProcessorNumber |Returns the current processor number when debugging spin lock usage in SMP machines.

### Timers
|Function|Description|
|---|---|
|oInitializeTimer |Associates a timer with the given device object and registers a driver-supplied IoTimer routine for the device object.
|IoStartTimer |Enables the timer for a given device object and calls the driver-supplied IoTimer routine once every second.
|IoStopTimer |Disables the timer for a given device object so the driver-supplied IoTimer routine is not called unless the driver reenables the timer.
|KeInitializeDpc |Initializes a DPC object and sets up a driver-supplied CustomTimerDpc routine that can be called with a given context.
|KeInitializeTimer |Initializes a notification timer object to the Not-Signaled state.
|KeInitializeTimerEx |Initializes a notification or synchronization timer object to the Not-Signaled state.
|KeSetTimer |Sets the absolute or relative interval at which a timer object will be set to the Signaled state; optionally supplies a timer DPC to be executed when the interval expires.
|KeSetTimerEx |Sets the absolute or relative interval at which a timer object will be set to the Signaled state; optionally supplies a timer DPC to be executed when the interval expires; and optionally supplies a recurring interval for the timer.
|KeCancelTimer |Cancels a timer object before the interval passed to KeSetTimer expires; dequeues a timer DPC before the timer interval, if any was set, expires.
|KeReadStateTimer |Returns TRUE if a given timer object is set to the Signaled state.
|KeQuerySystemTime |Returns the current system time.
|KeQueryRuntimeThread |Returns the accumulated kernel-mode and user-mode run time.
|KeQueryTickCount |Returns the number of interval-timer interrupts that have occurred since the system was booted.
|KeQueryTimeIncrement |Returns the number of 100-nanosecond units that are added to the system time at each interval-timer interrupt.
|KeQueryInterruptTime |Returns the current value of the system interrupt-time count in 100-nanosecond units, with accuracy to within system clock tick.
|KeQueryInterruptTimePrecise |Returns the current value of the system interrupt-time count in 100-nanosecond units, with accuracy to within a microsecond.
|KeQueryPerformanceCounter |Returns the system performance counter value in hertz. 


### Driver Threads, Dispatcher Objects, and Resources
|Function|Description|
|---|---|
|KeDelayExecutionThread |Puts the current thread into an alertable or nonalertable wait state for a given interval.
|ExInitializeResourceLite |Initializes a resource, for which the caller provides the storage, to be used for synchronization by a set of threads (shared readers, exclusive writers). 
|ExReinitializeResourceLite |Reinitializes an existing resource variable.
|ExAcquireResourceExclusiveLite |Acquires an initialized resource for exclusive access by the calling thread and optionally waits for the resource to be acquired.
|ExAcquireResourceSharedLite |Acquires an initialized resource for shared access by the calling thread and optionally waits for the resource to be acquired. 
|ExAcquireSharedStarveExclusive |Acquires a given resource for shared access without waiting for any pending attempts to acquire exclusive access to the same resource.
|ExAcquireSharedWaitForExclusive |Acquires a given resource for shared access, optionally waiting for any pending exclusive waiters to acquire and release the resource first. 
|ExIsResourceAcquiredExclusiveLite |Returns whether the calling thread has exclusive access to a given resource.
|ExIsResourceAcquiredSharedLite |Returns how many times the calling thread has acquired shared access to a given resource.
|ExGetExclusiveWaiterCount |Returns the number of threads currently waiting to acquire a given resource for exclusive access. 
|ExGetSharedWaiterCount |Returns the number of threads currently waiting to acquire a given resource for shared access. 
|ExConvertExclusiveToSharedLite |Converts a given resource from acquired for exclusive access to acquired for shared access.
|ExGetCurrentResourceThread |Returns the thread ID of the current thread.
|ExReleaseResourceForThreadLite |Releases a given resource that was acquired by the given thread.
|ExDeleteResourceLite |Deletes a caller-initialized resource from the system's resource list.
|IoQueueWorkItem |Queues an initialized work queue item so the driver-supplied routine will be called when a system worker thread is given control.
|KeSetTimer |Sets the absolute or relative interval at which a timer object will be set to the Signaled state, and optionally supplies a timer DPC to be executed when the interval expires.
|KeSetTimerEx |Sets the absolute or relative interval at which a timer object will be set to the Signaled state. Optionally supplies a timer DPC to be executed when the interval expires and a recurring interval for the timer.
|KeCancelTimer |Cancels a timer object before the interval passed to KeSetTimer expires. Dequeues a timer DPC before the timer interval (if any) expires.
|KeReadStateTimer |Returns TRUE if a given timer object is set to the Signaled state.
|KeSetEvent |Returns the previous state of a given event object and sets the event (if not already Signaled) to the Signaled state.
|KeClearEvent |Resets an event to the Not-Signaled state. 
|KeResetEvent |Returns the previous state of an event object and resets the event to the Not-Signaled state.
KeReadStateEvent |Returns the current state (nonzero for Signaled or zero for Not-Signaled) of a given event object.
|ExAcquireFastMutex |Acquires an initialized fast mutex, possibly after putting the caller into a wait state until it is acquired, and gives the calling thread ownership with APCs disabled. 
|ExTryToAcquireFastMutex |Acquires the given fast mutex immediately for the caller with APCs disabled, or returns FALSE. 
|ExReleaseFastMutex |Releases ownership of a fast mutex that was acquired with ExAcquireFastMutex or ExTryToAcquireFastMutex. 
|ExAcquireFastMutexUnsafe |Acquires an initialized fast mutex, possibly after putting the caller into a wait state until it is acquired. 
|ExReleaseFastMutexUnsafe |Releases ownership of a fast mutex that was acquired with ExAcquireFastMutexUnsafe. 
|KeReleaseMutex |Releases a given mutex object, specifying whether the caller will call one of the KeWaitXxx routines as soon as KeReleaseMutex returns the previous value of the mutex state (a zero for Signaled; otherwise, Not-Signaled).
|KeReadStateMutex |Returns the current state (one for Signaled or any other value for Not-Signaled) of a given mutex object.
|KeReleaseSemaphore |Releases a given semaphore object. Supplies a (run-time) priority boost for waiting threads if the release sets the semaphore to the Signaled state. Augments the semaphore count by a given value and specifies whether the caller will call one of the KeWaitXxx routines as soon as KeReleaseSemaphore returns.
|KeReadStateSemaphore |Returns the current state (zero for Not-Signaled or a positive value for Signaled) of a given semaphore object.
|KeWaitForSingleObject |Puts the current thread into an alertable or nonalertable wait state until a given dispatcher object is set to the Signaled state or (optionally) until the wait times out.
|KeWaitForMutexObject |Puts the current thread into an alertable or nonalertable wait state until a given mutex is set to the Signaled state or (optionally) until the wait times out.
|KeWaitForMultipleObjects |Puts the current thread into an alertable or nonalertable wait state until any one or all of a number of dispatcher objects are set to the Signaled state or (optionally) until the wait times out.
|PsGetCurrentThread |Returns a pointer to the current thread. 
|KeGetCurrentThread |Returns a pointer to the opaque thread object that represents the current thread. 
|IoGetCurrentProcess |Returns a pointer to the process of the current thread.
|PsGetCurrentProcess |Returns a pointer to the process of the current thread.
|KeEnterCriticalRegion |Temporarily disables the delivery of normal kernel APCs while a highest-level driver is running in the context of the user-mode thread that requested the current I/O operation. Special kernel-mode APCs are still delivered.
|KeLeaveCriticalRegion |Reenables, as soon as possible, the delivery of normal kernel-mode APCs that were disabled by a preceding call to KeEnterCriticalRegion.
|KeAreApcsDisabled |Returns TRUE if normal kernel-mode APCs are disabled.
|KeSaveFloatingPointState |Saves the current thread's nonvolatile floating-point context so that the caller can carry out its own floating-point operations.
|KeRestoreFloatingPointState |Restores the previous nonvolatile floating-point context that was saved with KeSaveFloatingPointState. 
|ZwSetInformationThread |Sets the priority of a given thread for which the caller has a handle.
|PsGetCurrentProcessId |Returns the system-assigned identifier of the current process. 
|PsGetCurrentThreadId |Returns the system-assigned identifier of the current thread. 
|PsSetCreateProcessNotifyRoutine |Registers a highest level driver's callback routine that is subsequently executed whenever a new process is created or existing process deleted.
|PsSetCreateThreadNotifyRoutine |Registers a highest level driver's callback routine that is subsequently executed whenever a new thread is created or an existing thread is deleted.
|PsSetLoadImageNotifyRoutine |Registers a callback routine for a highest level system-profiling driver. The callback routine is subsequently executed whenever a new image is loaded for execution. 

## Memory Allocation and Buffer Management
This section describes the Windows kernel routines and macros that kernel-mode drivers call to allocate memory and manage I/O buffers.

The Windows memory manager provides a set of routines that kernel-mode drivers use to allocate and manage memory. These routines have names that begin with the prefix Mm.

This section contains reference pages for the MmXxx routines and memory-management macros. These reference pages are listed in alphabetical order.

For an overview of the functionality of these routines and macros, see Memory Allocation and Buffer Management. For an introduction to memory management support for kernel-mode drivers, see Memory Management for Windows Drivers.

The following routines are reserved for system use. Do not use them in your driver.

- MmAddPhysicalMemory
- MmAddPhysicalMemoryEx
- MmAddVerifierThunks
- MmCreateMirror
- MmGetMdlBaseVa
- MmGetPhysicalMemoryRanges
- MmGetProcedureAddress
- MmGetVirtualForPhysical
- MmIsVerifierEnabled
- MmIsIoSpaceActive
- MmMapUserAddressesToPage
- MmMapVideoDisplay
- MmMapVideoDisplayEx
- MmMapViewInSessionSpace
- MmMapViewInSystemSpace
- MmMarkPhysicalMemoryAsBad
- MmMarkPhysicalMemoryAsGood
- MmProbeAndLockProcessPages
- MmRemovePhysicalMemory
- MmRemovePhysicalMemoryEx
- MmRotatePhysicalView
- MmUnmapVideoDisplay
- MmUnmapViewInSessionSpace
- MmUnmapViewInSystemSpace

For more information about memory allocation and buffer management, see Memory Management for Windows Drivers.

### Buffer Management
The short-term buffer management routines are called by kernel-mode drivers to allocate and free temporary buffers.

|Function|Description|
|---|---|
|ExAllocatePoolWithTag |Allocates (optionally cache-aligned) pool memory from paged or nonpaged system space. The caller-supplied tag is put into any crash dump of memory that occurs.
|ExAllocatePoolWithQuotaTag |Allocates pool memory, charging quota against the original requester of the I/O operation. The caller-supplied tag is put into any crash dump of memory that occurs. Only highest-level drivers can call this routine.
ExFreePool |Releases memory to paged or nonpaged system space.
|ExFreePoolWithTag |Releases memory with the specified pool tag.
|ExInitializeNPagedLookasideList |Initializes a lookaside list of nonpaged memory. After successful initialization of the list, fixed-size blocks can be allocated from, and freed to, the lookaside list.
|ExAllocateFromNPagedLookasideList |Removes the first entry from the specified lookaside list in nonpaged memory. If the lookaside list is empty, allocates an entry from nonpaged pool.
|ExFreeToNPagedLookasideList |Returns an entry to the specified lookaside list in nonpaged memory. If the list has reached its maximum size, returns the entry to nonpaged pool.
|ExDeleteNPagedLookasideList |Deletes a nonpaged lookaside list.
|ExInitializePagedLookasideList |Initializes a lookaside list of paged memory. After successful initialization of the list, fixed-size blocks can be allocated from and freed to the lookaside list.
|ExAllocateFromPagedLookasideList |Removes the first entry from the specified lookaside list in paged memory. If the lookaside list is empty, allocates an entry from paged pool.
|ExFreeToPagedLookasideList |Returns an entry to the specified lookaside list in paged memory. If the list has reached its maximum size, returns the entry to paged pool. 
|ExDeletePagedLookasideList |Deletes a paged lookaside list.
|MmQuerySystemSize |Returns an estimate (small, medium, or large) of the amount of memory available on the current platform.
|MmIsThisAnNtAsSystem |Returns TRUE if the machine is running as a server. If this routine returns TRUE, the caller is likely to require more resources to process I/O requests, and the machine is a server so it is likely to have more resources available.

### Long-Term Internal Driver Buffers
The long-term buffer management routines are called by kernel-mode drivers to allocate long-term driver-internal buffers.

|Function|Description|
|---|---|
|MmAllocateContiguousMemory |Allocates a range of physically contiguous, cache-aligned memory in nonpaged pool.
|MmFreeContiguousMemory |Releases a range of physically contiguous memory when the driver unloads.
|MmAllocateNonCachedMemory |Allocates a virtual address range of noncached and cache-aligned memory in nonpaged system space (pool).
|MmFreeNonCachedMemory |Releases a virtual address range of noncached memory in nonpaged system space when the driver unloads.
|MmAllocateMappingAddress |Reserves a range of virtual address space that can later be mapped with MmMapLockedPagesWithReservedMapping.
|MmFreeMappingAddress |Frees a reserved memory address reserved by MmAllocateMappingAddress.
|AllocateCommonBuffer |Allocates and maps a logically contiguous region of memory that is simultaneously accessible both from the processor and from a device, given access to an adapter object, the requested length of the memory region to allocate, and access to variables where the starting logical and virtual addresses of the allocated region are returned. Returns TRUE if the requested length was allocated. Can be used for continuous bus-master DMA or for system DMA using the autoinitialize mode of a system DMA controller.
|FreeCommonBuffer |Releases an allocated common buffer and unmaps it, given access to the adapter object, the length, and the starting logical and virtual addresses of the region to be freed when the driver unloads. Arguments must match those passed in the call to AllocateCommonBuffer.

### Buffered Data and Buffer Initialization
The buffered-data and buffer-initialization routines are called by kernel-mode drivers to manage buffered data or initialize driver-allocated buffers.

|Function|Description|
|---|---|
RtlCompar|Memory |Compares data, given pointers to caller-supplied buffers and the length in bytes for the comparison. Returns the number of bytes that are equal.
|RtlCopyMemory |Copies the data from one caller-supplied buffer to another, given pointers to both buffers and the length in bytes to be copied.
|RtlMoveMemory |Copies the data from one caller-supplied memory range to another, given pointers to the base of both ranges and the length in bytes to be copied.
|RtlFillMemory |Fills a caller-supplied buffer with the specified UCHAR value, given a pointer to the buffer and the length in bytes to be filled.
|RtlZeroMemory |Fills a buffer with zeros, given a pointer to the caller-supplied buffer and the length in bytes to be filled.
|RtlStoreUshort |Stores a USHORT value at a given address, avoiding alignment faults.
|RtlRetrieveUshort |Retrieves a USHORT value at a given address, avoiding alignment faults, and stores the value at a given address that is assumed to be aligned.
|RtlStoreUlong |Stores a ULONG value at a given address, avoiding alignment faults.
|RtlRetrieveUlong |Retrieves a ULONG value at a given address, avoiding alignment faults, and stores the value at a given address that is assumed to be aligned. 

 
### Address Mappings and MDLs
The address-mapping and MDL-management routines are called by kernel-mode drivers to manage address mappings and memory descriptor lists (MDLs).

|Function|Description|
|---|---|
|oAllocateMdl |Allocates an MDL large enough to map the starting address and length supplied by the caller; optionally associates the MDL with a given IRP.
|IoBuildPartialMdl |Builds an MDL for the specified starting virtual address and length in bytes from a given source MDL. Drivers that split large transfer requests into a number of smaller transfers can call this routine.
|IoFreeMdl |Releases a given MDL allocated by the caller.
|MmAllocatePagesForMdlEx |Allocates nonpaged, physical memory pages for an MDL.
|MmBuildMdlForNonPagedPool |Fills in the corresponding physical addresses of a given MDL that specifies a range of virtual addresses in nonpaged pool.
|MmCreateMdl |Obsolete. Allocates and initializes an MDL describing a buffer specified by the given virtual address and length in bytes; returns a pointer to the MDL.
|MmGetMdlByteCount |Returns the length in bytes of the buffer mapped by a given MDL.
|MmGetMdlByteOffset |Returns the byte offset within a page of the buffer described by a given MDL.
|MmGetMdlVirtualAddress |Returns a (possibly invalid) virtual address for a buffer described by a given MDL; the returned address, used as an index to a physical address entry in the MDL, can be input to MapTransfer for drivers that use DMA.
|MmGetPhysicalAddress |Returns the corresponding physical address for a given valid virtual address.
|MmGetSystemAddressForMdlSafe |Returns a system-space virtual address that maps the physical pages described by a given MDL for drivers whose devices must use programmed I/O (PIO). If no virtual address exists, one is assigned.
|MmInitializeMdl |Initializes a caller-created MDL to describe a buffer specified by the given virtual address and length in bytes.
|MmIsAddressValid |Returns whether a page fault will occur if a read or write operation is done at the given virtual address.
|MmMapIoSpace |Maps a physical address range to a cached or noncached virtual address range in nonpaged system space.
|MmMapLockedPages |Obsolete. Maps already locked physical pages, described by a given MDL, to a returned virtual address range.
|MmMapLockedPagesWithReservedMapping |Maps a virtual address range already reserved with MmAllocateMappingAddress.
|MmPrepareMdlForReuse |Reinitializes a caller-created MDL for reuse.
|MmProbeAndLockPages |Probes the pages specified in an MDL for a particular kind of access, makes the pages resident, and locks them in memory; returns the MDL updated with corresponding physical addresses. (Usually, only highest-level drivers call this routine.)
|MmProtectMdlSystemAddress |Sets the protection type for the memory-address range.
|MmSecureVirtualMemory |Secures a memory-address range so that it cannot be freed and its page protection cannot be made more restrictive.
|MmSizeOfMdl |Returns the number of bytes required for an MDL describing the buffer specified by the given virtual address and length in bytes.
|MmUnlockPages |Unlocks the previously probed and locked pages specified in an MDL.
|MmUnmapIoSpace |Unmaps a virtual address range from a physical address range.
|MmUnmapLockedPages |Releases a mapping set up by MmMapLockedPages.
|MmUnmapReservedMapping |Unmaps a virtual address range mapped by MmMapLockedPagesWithReservedMapping.
|MmUnsecureVirtualMemory Unsecures a memory-address range secured by MmSecureVirtualMemory.

### Buffer and MDL Management
The buffer- and MDL-management macros are called by kernel-mode drivers to manage buffers and memory descriptor lists (MDLs).

For more information about MDLs, see Using MDLs.

|Function|Description|
|---|---|
ADDRESS_A|D_SIZE_TO_SPAN_PAGES |Returns the number of pages required to contain a given virtual address and size in bytes.
|BYTE_OFFSET |Returns the byte offset of a given virtual address within the page.
|BYTES_TO_PAGES |Returns the number of pages necessary to contain a given number of bytes.
|PAGE_ALIGN |Returns the page-aligned virtual address for the page that contains a given virtual address.
|ROUND_TO_PAGES |Rounds a given size in bytes up to a page-size multiple.

### Device Memory Access
The device-memory-access macros are called by kernel-mode drivers to access the memory-mapped hardware registers and I/O ports of their respective devices.

For the following macros, XXX_REGISTER_XXX indicates device memory that is mapped onto system memory address space, while XXX_PORT_XXX indicates device memory in I/O port address space.

|Function|Description|
|---|---|
|EAD_PORT_UCHAR |Reads a UCHAR value from the given I/O port address.
|READ_PORT_USHORT |Reads a USHORT value from the given I/O port address.
|READ_PORT_ULONG |Reads a ULONG value from the given I/O port address.
|READ_PORT_BUFFER_UCHAR |Reads a given count of UCHAR values from the given I/O port into a given buffer.
|READ_PORT_BUFFER_USHORT |Reads a given count of USHORT values from the given I/O port into a given buffer.
|READ_PORT_BUFFER_ULONG |Reads a given count of ULONG values from the given I/O port into a given buffer.
|WRITE_PORT_UCHAR |Writes a given UCHAR value to the given I/O port address.
|WRITE_PORT_USHORT |Writes a given USHORT value to the given I/O port address.
|WRITE_PORT_ULONG |Writes a given ULONG value to the given I/O port address.
|WRITE_PORT_BUFFER_UCHAR |Writes a given count of UCHAR values from a given buffer to the given I/O port.
|WRITE_PORT_BUFFER_USHORT |Writes a given count of USHORT values from a given buffer to the given I/O port.
|WRITE_PORT_BUFFER_ULONG |Writes a given count of ULONG values from a given buffer to the given I/O port.
|READ_REGISTER_UCHAR |Reads a UCHAR value from the given register address in memory space.
|READ_REGISTER_USHORT |Reads a USHORT value from the given register address in memory space.
|READ_REGISTER_ULONG |Reads a ULONG value from the given register address in memory space.
|READ_REGISTER_BUFFER_UCHAR |Reads a given count of UCHAR values from the given register address into the given buffer.
|READ_REGISTER_BUFFER_USHORT |Reads a given count of USHORT values from the given register address into the given buffer.
|READ_REGISTER_BUFFER_ULONG |Reads a given count of ULONG values from the given register address into the given buffer.
|WRITE_REGISTER_UCHAR |Writes a given UCHAR value to the given register address in memory space.
|WRITE_REGISTER_USHORT |Writes a given USHORT value to the given register address in memory space.
|WRITE_REGISTER_ULONG |Writes a given ULONG value to the given register address in memory space.
|WRITE_REGISTER_BUFFER_UCHAR |Writes a given count of UCHAR values from a given buffer to the given register address.
|WRITE_REGISTER_BUFFER_USHORT |Writes a given count of USHORT values from a given buffer to the given register address.
|WRITE_REGISTER_BUFFER_ULONG |Writes a given count of ULONG values from a given buffer to the given register address.

 
### Pageable Drivers
The pageable-driver routines are called by kernel-mode drivers to lock and unlock a driver's pageable code or data sections, or make an entire driver pageable.

|Function|Description|
|---|---|
M|LockPagableCodeSection |Locks a set of driver routines marked with a special compiler directive into system space.
|MmLockPagableDataSection |Locks data marked with a special compiler directive into system space, when that data is accessed infrequently, predictably, and at an IRQL of less than DISPATCH_LEVEL.
|MmLockPagableSectionByHandle |Locks a pageable section into system memory using a handle returned from MmLockPagableCodeSection or MmLockPagableDataSection.
|MmUnlockPagableImageSection |Releases a section that was previously locked into system space when the driver is no longer processing IRPs, or when the contents of the section are no longer required.
|MmPageEntireDriver |Lets a driver page all of its code and data regardless of the attributes of the various sections in the driver's image.
|MmResetDriverPaging |Resets a driver's pageable status to that specified by the sections making up the driver's image.


### Sections and Views
The section- and view-management routines are called by kernel-mode drivers to set up mapped sections and views of memory.

|Function|Description|
|---|---|
|nitializeObjectAttributes |Sets up a parameter of type OBJECT_ATTRIBUTES for a subsequent call to a ZwCreateXxx or ZwOpenXxx routine.
|ZwOpenSection |Obtains a handle for an existing section, provided that the requested access can be allowed.
|ZwMapViewOfSection |Maps a view of an open section into the virtual address space of a process. Returns an offset into the section (base of the mapped view) and the size mapped.
|ZwUnmapViewOfSection |Releases a mapped view in the virtual address space of a process.

### Access to Structures
The structure-access macros are called by kernel-mode drivers to access parts of structures.

|Function|Description|
|---|---|
|RGUMENT_PRESENT |Returns FALSE if an argument pointer is NULL; otherwise returns TRUE.
|CONTAINING_RECORD| Returns the base address of an instance of a structure given the structure type and the address of a field within it.
|FIELD_OFFSET |Returns the byte offset of a named field in a known structure type.

 
## Plug and Play Routines
These routines are used by drivers to implement Plug and Play (PnP) support. For background and task-oriented information about supporting PnP in drivers, see Plug and Play.


The following topics summarize the routines by functionality:

### Device Information Routines
|Function|Description|
|---|---|
|oGetDeviceProperty |Retrieves information about a device such as configuration information and the name of its PDO.
|IoInvalidateDeviceRelations |Notifies the PnP manager that the relations for a device have changed.
|IoInvalidateDeviceState |Notifies the PnP manager that the PnP state of a device has changed. In response, the PnP manager sends an IRP_MN_QUERY_PNP_DEVICE_STATE to the device stack.
|IoReportDetectedDevice |Reports a non-PnP device to the PnP manager.
|IoReportResourceForDetection |Claims hardware resources in the configuration registry for a legacy device. This routine is for drivers that detect legacy hardware that cannot be enumerated by PnP.


### Registry Routines
|Function|Description|
|---|---|
|oOpenDeviceInterfaceRegistryKey |Returns a handle to a registry key for storing information about a particular device interface.
|IoOpenDeviceRegistryKey |Returns a handle to a device-specific or a driver-specific registry key for a particular device instance. 

### Device Interface Routines
|Function|Description|
|---|---|
|IoRegisterDeviceInterface |Registers device functionality (a device interface) that a driver will enable for use by applications or other system components.
|IoSetDeviceInterfaceState |Enables or disables a previously registered device interface. Applications and other system components can open only interfaces that are enabled.
|IoOpenDeviceInterfaceRegistryKey |Returns a handle to a registry key for storing information about a particular device interface.
|IoGetDeviceInterfaces |Returns a list of device interfaces of a particular device interface class (such as all devices on the system that support a HID interface).
|IoGetDeviceInterfaceAlias |Returns the alias device interface of the specified interface class, if the alias exists. Device interfaces are considered aliases if they are exposed by the same underlying device and have identical interface reference strings, but are of different interface classes.

 
### PnP Notification Routines
|Function|Description|
|---|---|
|IoRegisterPlugPlayNotification |Registers a driver callback routine to be called when the specified PnP event occurs.
|IoReportTargetDeviceChange |Notifies the PnP manager that a custom event has occurred on a device. The PnP manager sends notification of the event to drivers that registered for it. Do not use this routine to report system PnP events, such as GUID_TARGET_DEVICE_REMOVE_COMPLETE.
|IoReportTargetDeviceChangeAsynchronous |Notifies the PnP manager that a custom event has occurred on a device. Returns immediately and does not wait while the PnP manager sends notification of the event to drivers that registered for it. Do not use this routine to report system PnP events, such as GUID_TARGET_DEVICE_REMOVE_COMPLETE.
|IoUnregisterPlugPlayNotification |Removes the registration of a driver's callback routine for a PnP event.

### Remove Lock Routines
|Function|Description|
|---|---|
|oInitializeRemoveLock |Initializes a remove lock for a device object. A driver can use the lock to track outstanding I/O on a device and to determine when the driver can delete its device object in response to an IRP_MN_REMOVE_DEVICE request.
|IoAcquireRemoveLock |Increments the count for a remove lock, indicating that the associated device object should not be detached from the device stack nor deleted.
|IoReleaseRemoveLock |Releases a remove lock acquired with a previous call to IoAcquireRemoveLock. 
|IoReleaseRemoveLockAndWait |Releases a remove lock acquired with a previous call to IoAcquireRemoveLock and waits until all acquisitions of the lock have been released. A driver typically calls this routine in its dispatch code for an IRP_MN_REMOVE_DEVICE request. 

### Other PnP Routines
|Function|Description|
|---|---|
|oAdjustPagingPathCount |Increments or decrements a caller-supplied page-file counter as an atomic operation. This routine can be used to adjust other counters, such as counters for hibernation files or crash-dump files.
|IoRequestDeviceEject |Notifies the PnP manager that the device eject button was pressed. Note that this routine reports a request for a device eject, not media eject.

## Windows Management Instrumentation Routines
This section summarizes kernel-mode support routines that drivers can use to interact with Windows Management Instrumentation (WMI).

The categories of support routines include those that drivers can call to:

-   Process IRPs that a driver receives (WMI IRP Processing Routines).
|Function|Description|
|---|---|
|WmiCompleteRequest |If a driver uses WmiSystemControl to dispatch the WMI IRP to a callback routine, then the callback routine can use WmiCompleteRequest to complete the IRP.
|WmiSystemControl Dispatches a WMI IRP to a driver-supplied callback routine.
|WmiFireEvent| The WmiFireEvent routine sends an event to WMI for delivery to data consumers that have requested notification of the event.
|WmiQueryTraceInformation| The WmiQueryTraceInformation routine returns information about a WMI event trace.
|WmiSystemControl| The WmiSystemControl routine is a dispatch routine for drivers that use WMI library support routines to handle WMI IRPs.
|WmiTraceMessage| The WmiTraceMessage routine adds a message to the output log of a WPP software tracing session.
|WmiTraceMessageVa| The WmiTraceMessageVa routine adds a message to the output log of a WPP software tracing session.

-   Drivers can use these routines in processing WMI IRPs.
Drivers use these routines to send WMI IRPs.
|Function|Description|
|---|---|
|IoWMIAllocateInstanceIds |Allocates unused WMI instance IDs for a given WMI class GUID.
|IoWMIDeviceObjectToInstanceName |Given a device object, determines the WMI class instance name supported by the corresponding driver. Callers can use this to determine the instance names supported by a particular driver.
|IoWMIExecuteMethod |Executes the specified WMI class method.
|IoWMIHandleToInstanceName |Given a file handle, determines the WMI class instance name supported by the corresponding driver. Callers can use this to determine the instance names supported by a particular driver.
|IoWMIOpenBlock |Opens a WMI data block. Callers use this to submit WMI I/O requests.
|IoWMIQueryAllData |Fetches the property values for every instance of the specified WMI class GUID.
|IoWMIQueryAllDataMultiple |Fetches the property values for every instance of the specified set of WMI class GUIDs.
|IoWMIQuerySingleInstance |Fetches the property values for a particular instance of the specified WMI class GUID.
|IoWMIQuerySingleInstanceMultiple |Fetches the property values for a particular set of WMI class instances.
|IoWMISetNotificationCallback |Sets a notification callback for WMI events.
|IoWMISetSingleInstance |Sets the property values for a particular WMI class instance.
|IoWMISetSingleItem |Sets the specified property for a particular WMI class instance.

This section describes required and optional routines that a kernel-mode WDM driver contains, if the driver handles WMI Minor IRPs by calling WmiSystemControl. For more information, see Calling WmiSystemControl to Handle WMI IRPs.

The DpWmiXxx names that are used in the Microsoft Windows Driver Kit (WDK) documentation are placeholders. A driver's DpWmiXxx routines can have any names that the driver writer chooses. 


## ZwXxx / NtXxx Routines
The ZwXxx routines provide a set of system entry points that parallel some of the executive's system services. Calling a ZwXxx routine from kernel-mode code results in a call to the corresponding system service. Calling a ZwXxx routine from user mode is not supported; instead, native applications (applications that bypass the Microsoft Win32 subsystem) should call the NtXxx equivalent of the ZwXxx routine.

For a list of NtXxx routines, see NtXxx Routines.

For a call to a ZwXxx routine from a kernel-mode driver, the system does not check the caller's access rights, nor does it set the previous processor mode to UserMode. Before calling a ZwXxx routine, a kernel-mode driver must check all user-supplied parameters for validity.

For more information about the relationship between NtXxx and ZwXxx routines, see Using Nt and Zw Versions of the Native System Services Routines. For a list of the ZwXxx routines in each major functional category, see Summary of Kernel-Mode Support Routines.

The following routines are reserved for system use. Do not use them in your driver.

|Routine|Replacement|
|ZwCancelTimer| Use KeCancelTimer instead.|
|ZwCreateTimer| Use KeInitializeTimer or KeInitializeTimerEx instead.|
|ZwOpenTimer.||
|ZwSetTimer| Use KeSetTimer instead.|
|NtRenameTransactionManager| Obsolete.|

> [!NOTE]
> NtRenameTransactionManager and TmRenameTransactionManager are two versions of the same routine. Kernel-mode drivers should not call NtRenameTransactionManager. They should instead call TmRenameTransactionManager. 
 
|Function|Description|
|---|---|
|NtRenameTransactionManager| The NtRenameTransactionManager routine changes the identity of the transaction manager object that is stored in the CLFS log file stream contained in the log file name.
|NtSetInformationTransactionManager Do not call this routine from kernel-mode code.
|ZwAllocateLocallyUniqueId| The ZwAllocateLocallyUniqueId routine allocates a locally unique identifier (LUID). 
|ZwAllocateVirtualMemory| The ZwAllocateVirtualMemory routine reserves, commits, or both, a region of pages within the user-mode virtual address space of a specified process.
|ZwClose| The ZwClose routine closes an object handle. 
|ZwCreateDirectoryObject| The ZwCreateDirectoryObject routine creates or opens an object-directory object.
|ZwCreateEvent| The ZwCreateEvent routine creates an event object, sets the initial state of the event to the specified value, and opens a handle to the object with the specified desired access.
|ZwCreateFile| The ZwCreateFile routine creates a new file or opens an existing file.
|ZwCreateKey| The ZwCreateKey routine creates a new registry key or opens an existing one.
|ZwCreateKeyTransacted| The ZwCreateKeyTransacted routine creates a new registry key or opens an existing one, and it associates the key with a transaction. 
|ZwCreateSection| The ZwCreateSection routine creates a section object.
|ZwDeleteFile| The ZwDeleteFile routine deletes the specified file.
|ZwDeleteKey| The ZwDeleteKey routine deletes an open key from the registry.
|ZwDeleteValueKey| The ZwDeleteValueKey routine deletes a value entry matching a name from an open key in the registry. If no such entry exists, an error is returned. 
|ZwDeviceIoControlFile| The ZwDeviceIoControlFile routine sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified operation.
|ZwDuplicateToken| The ZwDuplicateToken function creates a handle to a new access token that duplicates an existing token. This function can create either a primary token or an impersonation token. 
|ZwEnumerateKey| The ZwEnumerateKey routine returns information about a subkey of an open registry key.
|ZwEnumerateValueKey| The ZwEnumerateValueKey routine gets information about the value entries of an open key.
|ZwFlushBuffersFile| The ZwFlushBuffersFile routine is called by a file system filter driver to send a flush request for the specified file to the file system.
|ZwFlushBuffersFileEx| The ZwFlushBuffersFileEx routine is called by a file system filter driver to send a flush request for a given file to the file system. An optional flush operation flag can be set to control how file data is written to storage.
|ZwFlushKey|The ZwFlushKey routine forces a registry key to be committed to disk.
|ZwFlushVirtualMemory| The ZwFlushVirtualMemory routine flushes a range of virtual addresses within the virtual address space of a specified process which map to a data file back out to the data file if they have been modified.
|ZwFreeVirtualMemory|The ZwFreeVirtualMemory routine releases, decommits, or both, a region of pages within the virtual address space of a specified process.
|ZwFsControlFile| The ZwFsControlFile routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action.
|ZwLoadDriver| The ZwLoadDriver routine loads a driver into the system. 
|ZwLockFile| The ZwLockFile routine requests a byte-range lock for the specified file.
|ZwMakeTemporaryObject| The ZwMakeTemporaryObject routine changes the attributes of an object to make it temporary.
|ZwMapViewOfSection| The ZwMapViewOfSection routine maps a view of a section into the virtual address space of a subject process.
|ZwNotifyChangeKey| The ZwNotifyChangeKey routine allows a driver to request notification when a registry key changes.
|ZwOpenEvent| The ZwOpenEvent routine opens a handle to an existing named event object with the specified desired access.
|ZwOpenFile| The ZwOpenFile routine opens an existing file, directory, device, or volume.
|ZwOpenKey| The ZwOpenKey routine opens an existing registry key. 
|ZwOpenKeyEx| The ZwOpenKeyEx routine opens an existing registry key. 
|ZwOpenKeyTransacted| The ZwOpenKeyTransacted routine opens an existing registry key and associates the key with a transaction. 
|ZwOpenKeyTransactedEx| The ZwOpenKeyTransactedEx routine opens an existing registry key and associates the key with a transaction. 
|ZwOpenProcess| The ZwOpenProcess routine opens a handle to a process object and sets the access rights to this object.
|ZwOpenProcessTokenEx| The ZwOpenProcessTokenEx routine opens the access token associated with a process. 
|ZwOpenSection| The ZwOpenSection routine opens a handle for an existing section object.
|ZwOpenSymbolicLinkObject| The ZwOpenSymbolicLinkObject routine opens an existing symbolic link.
|ZwOpenThreadTokenEx| The ZwOpenThreadTokenEx routine opens the access token associated with a thread. 
|ZwPowerInformation| The ZwPowerInformation routine sets or retrieves system power information.
|ZwQueryInformationThread| The ZwQueryInformationThread routine retrieves information about the specified thread, such as its page priority.
|ZwQueryDirectoryFile| The ZwQueryDirectoryFile routine returns various kinds of information about files in the directory specified by a given file handle.
|ZwQueryEaFile| The ZwQueryEaFile routine returns information about extended-attribute (EA) values for a file.
|ZwQueryFullAttributesFile| The ZwQueryFullAttributesFile routine supplies network open information for the specified file.
|ZwQueryInformationFile| The ZwQueryInformationFile routine returns various kinds of information about a file object.
|ZwQueryInformationToken| The ZwQueryInformationToken routine retrieves a specified type of information about an access token. The calling process must have appropriate access rights to obtain the information. 
|ZwQueryKey| The ZwQueryKey routine provides information about the class of a registry key, and the number and sizes of its subkeys.
|ZwQueryObjec| The ZwQueryObject routine provides information about a supplied object.
|ZwQueryQuotaInformationFile| The ZwQueryQuotaInformationFile routine retrieves quota entries associated with the volume specified by the FileHandle parameter. 
|ZwQuerySecurityObject| The ZwQuerySecurityObject routine retrieves a copy of an object's security descriptor. 
|ZwQuerySymbolicLinkObject| The ZwQuerySymbolicLinkObject routine returns a Unicode string that contains the target of a symbolic link.
|ZwQueryValueKey| The ZwQueryValueKey routine returns a value entry for a registry key.
|ZwQueryVirtualMemory| The ZwQueryVirtualMemory routine determines the state, protection, and type of a region of pages within the virtual address space of the subject process.
|ZwQueryVolumeInformationFile| The ZwQueryVolumeInformationFile routine retrieves information about the volume associated with a given file, directory, storage device, or volume.
|ZwReadFile| The ZwReadFile routine reads data from an open file. 
|ZwSetEaFile| The ZwSetEaFile routine sets extended-attribute (EA) values for a file.
|ZwSetEvent| The ZwSetEvent routine sets an event object to a Signaled state and attempts to satisfy as many waits as possible.
|ZwSetInformationFile| The ZwSetInformationFile routine changes various kinds of information about a file object.
|ZwSetInformationThread| The ZwSetInformationThread routine sets the priority of a thread.
|ZwSetInformationToken The ZwSetInformationToken routine modifies information in a specified token. The calling process must have appropriate access rights to set the information. 
|ZwSetInformationVirtualMemory| The ZwSetInformationVirtualMemory routine performs an operation on a specified list of address ranges in the user address space of a process. 
|ZwSetQuotaInformationFile| The ZwSetQuotaInformationFile routine changes quota entries for the volume associated with the FileHandle parameter. All of the quota entries in the specified buffer are applied to the volume. 
|ZwSetSecurityObject| The ZwSetSecurityObject routine sets an object's security state.
|ZwSetValueKey| The ZwSetValueKey routine creates or replaces a registry key's value entry.
|ZwSetVolumeInformationFile| The ZwSetVolumeInformationFile routine modifies information about the volume associated with a given file, directory, storage device, or volume. 
|ZwTerminateProcess| The ZwTerminateProcess routine terminates a process and all of its threads.
|ZwUnloadDriver| The ZwUnloadDriver routine unloads a driver from the system. Use this routine with extreme caution. (See the following Remarks section.)
|ZwUnlockFile| The ZwUnlockFile routine unlocks a byte-range lock in a file.
|ZwUnmapViewOfSection| The ZwUnmapViewOfSection routine unmaps a view of a section from the virtual address space of a subject process.
|ZwWaitForSingleObject| The ZwWaitForSingleObject routine waits until the specified object attains a state of Signaled. An optional time-out can also be specified.
|ZwWriteFile| The ZwWriteFile routine writes data to an open file.
 
## Auxiliary Kernel-Mode Library Routines and Structures
The Auxiliary Kernel-Mode Library enables drivers to access some system capabilities that are not available from kernel-mode subsystems.

The AuxKlibInitialize routine initializes the Auxiliary Kernel-Mode Library. Drivers that use this library must call AuxKlibInitialize before calling any of the library's other routines.


- AuxKlibEnumerateSystemFirmwareTables
- AuxKlibGetBugCheckData
- AuxKlibGetImageExportDirectory
- AuxKlibGetSystemFirmwareTable
- AuxKlibInitialize
- AuxKlibQueryModuleInformation
- AUX_MODULE_BASIC_INFO
- AUX_MODULE_EXTENDED_INFO
- KBUGCHECK_DATA

 
## Processor Group Compatibility Library
Support is available for kernel-mode drivers that use processor groups. The Processor Group (ProcGrp) compatibility library enables a kernel-mode driver that is written to use processor groups run on earlier versions of Windows, which do not support processor groups. When this driver runs on, it can take advantage of multiple processor groups, if the hardware platform supports them. When this same driver runs on an earlier version of Windows, it is limited to a single processor group, regardless of the capabilities of the hardware platform. To use the ProcGrp library, the driver must call a library initialization routine. Additionally, the driver must be compiled for the Windows 7 environment in the WDK, and must be linked with Procgrp.lib.

The ProcGrp library is designed to meet the compatibility requirements of drivers that call the following KeXxx routines but must also run on versions of Windows that do not implement these routines:

- KeGetCurrentProcessorNumberEx
- KeGetProcessorIndexFromNumber
- KeGetProcessorNumberFromIndex
- KeQueryActiveGroupCount
- KeQueryActiveProcessorCountEx
- KeQueryGroupAffinity
- KeQueryMaximumProcessorCount
- KeQueryMaximumProcessorCountEx
- KeQueryMaximumGroupCount
- KeSetSystemAffinityThreadEx
- KeSetSystemGroupAffinityThread
- KeRevertToUserAffinityThreadEx
- KeRevertToUserGroupAffinityThread
- KeSetTargetProcessorDpcEx

The ProcGrp library implements wrapper functions for the KeXxx routines in the preceding list. If the library runs on Windows 7 or Windows Server 2008 R2, the wrapper functions simply call the corresponding KeXxx routines. The wrapper functions have the same names as these KeXxx routines, and their behavior is identical to that of the KeXxx routines that they replace.

Earlier versions of Windows do not support processor groups and do not implement the KeXxx routines in the preceding list. If the ProcGrp library is linked to a driver that runs on one of these earlier versions of Windows, the library initialization function, WdmlibProcgrpInitialize, detects that the operating system does not support processor groups. To deal with this case, each wrapper function contains a simplified implementation of the corresponding KeXxx routine. This implementation supports only one processor group, group number 0. For example, the wrapper function for the KeQueryMaximumGroupCount routine always returns a count of one. For another example, the wrapper function for the KeGetCurrentProcessorNumberEx routine emulates this routine by calling the KeGetCurrentProcessorNumber routine. KeGetCurrentProcessorNumber is similar to KeGetCurrentProcessorNumberEx, but lacks support for processor groups, which, in this case, has the same effect as supporting just one processor group.

For more information about the support for processor groups in Windows 7, see the [Supporting Systems That Have More Than 64 Processors white paper](https://download.microsoft.com/download/a/d/f/adf1347d-08dc-41a4-9084-623b1194d4b2/MoreThan64proc.docx) on the WHDC website.

The ProcGrp library is contained in the Windows 7 version of the WDK. The library functions are declared in the Procgrp.h header file and are implemented in the Procgrp.lib library file. 

In addition to the KeXxx wrapper functions, the ProcGrp library implements the following function to initialize the library:

- WdmlibProcgrpInitialize





## DMA

DMA Library Routines
Drivers use the routines documented in this section to perform direct memory access (DMA) operations. The routines are accessed through pointers and cannot be called directly by name.

Drivers performing DMA operations use IoGetDmaAdapter to get a pointer to the DMA_ADAPTER structure for the device. The DmaOperations member of the structure points to a DMA_OPERATIONS structure, which is a table of pointers to the DMA routines for the physical device object of that device.


|Function|Description|
|---|---|
|IoGetDmaAdapter |Returns a pointer to an adapter object that represents either the DMA channel to which the driver's device is connected or the driver's bus-master adapter. Also returns the maximum number of map registers the driver can specify for each DMA transfer.
|MmGetMdlVirtualAddress |Returns the base virtual address of a buffer described by a given MDL. The returned address, used as an index to a physical address entry in the MDL, can be input to MapTransfer.
|MmGetSystemAddressForMdlSafe |Returns a nonpaged system-space virtual address for the base of the memory area described by an MDL. It maps the physical pages described by the MDL into system space, if they are not already mapped to system space. 
|ADDRESS_AND_SIZE_TO_SPAN_PAGES |Returns the number of pages spanned by the virtual range defined by a virtual address and a length in bytes. A driver can use this macro to determine whether a transfer request must be split into partial transfers.
|AllocateAdapterChannel |Reserves exclusive access to a DMA channel and map registers for a device. When the channel and registers are available, this routine calls a driver-supplied AdapterControl routine to carry out an I/O operation through either the system DMA controller or a bus-master adapter.
|AllocateCommonBuffer |Allocates and maps a logically contiguous region of memory that is simultaneously accessible from both the processor and a device. This routine returns TRUE if the requested length was allocated.
|BuildMdlFromScatterGatherList |Builds an MDL corresponding to a scatter/gather list.
|BuildScatterGatherList |Prepares the system for scatter/gather DMA for a device and calls a driver-supplied routine to carry out the I/O operation. This function provides the same functionality as GetScatterGatherList, except it uses a driver-supplied buffer to hold the scatter/gather list.
|CalculateScatterGatherList |Computes the buffer size needed to hold a scatter/gather list for a memory buffer.
|FlushAdapterBuffers |Forces any data remaining in either a bus-master adapter's or the system DMA controller's internal buffers to be written into memory or to the device.
|FreeAdapterChannel |Releases an adapter object that represents a system DMA channel, and optionally releases any allocated map registers.
|FreeCommonBuffer |Releases and unmaps a previously allocated common buffer. Arguments must match those passed in an earlier call to AllocateCommonBuffer.
|FreeMapRegisters |Releases a set of map registers that were saved from a call to AllocateAdapterChannel. A driver calls this routine after using the registers in one or more calls to MapTransfer, flushing the cache by calling FlushAdapterBuffers, and completing the bus-master DMA transfer.
|GetDmaAlignment |Returns the buffer alignment requirements for a DMA controller or device.
|GetScatterGatherList |Prepares the system for scatter/gather DMA for a device and calls a driver-supplied routine to carry out the I/O operation. For devices that support scatter/gather DMA, this routine combines the functionality of AllocateAdapterChannel and MapTransfer.
|KeFlushIoBuffers |Flushes the memory region described by an MDL from all processors' caches into memory.
|MapTransfer |Sets up map registers for an adapter object previously allocated by AllocateAdapterChannel to map a transfer from a locked-down buffer. Returns the logical address of the mapped region and, for bus-master devices that support scatter/gather, the number of bytes mapped.
|PutDmaAdapter |Frees an adapter object previously allocated by IoGetDmaAdapter.
|PutScatterGatherList |Frees map registers and scatter/gather list previously allocated by GetScatterGatherList. 
|ReadDmaCounter Returns the number of bytes yet to be transferred during the current system DMA operation (in autoinitialize mode).

## PIO
|Function|Description|
|---|---|
|MmProbeAndLockPages |Probes the pages specified in an MDL for a particular kind of access, makes the pages resident, and locks them in memory; returns the MDL updated with corresponding physical addresses.
|MmGetSystemAddressForMdlSafe |Returns a system-space virtual address that maps the physical pages described by a given MDL for drivers whose devices must use PIO. If no virtual address exists, one is assigned.
|KeFlushIoBuffers |Flushes the memory region described by a given MDL from all processors' caches into memory.
|MmUnlockPages |Unlocks the previously probed and locked pages specified in an MDL.
|MmMapIoSpace |Maps a physical address range to a cached or noncached virtual address range in nonpaged system space.
|MmUnmapIoSpace |Unmaps a virtual address range from a physical address range.

## Interrupts
|Function|Description|
|---|---|
|IoConnectInterrupt |Registers a driver's interrupt handling routine. Drivers should use IoConnectInterruptEx instead. 
|IoDisconnectInterrupt |Unregisters an interrupt handling routine that IoConnectInterrupt registered.
|IoConnectInterruptEx |Registers a driver's interrupt handling routine. Drivers can register either an InterruptService routine for line-based interrupts or an InterruptMessageService routine for message-signaled interrupts.
|IoDisconnectInterruptEx |Unregisters an interrupt-handling routine that IoConnectInterruptEx registered.
|IoInitializeDpcRequest |Associates a driver-supplied DpcForIsr routine with a given device object, so that the DpcForIsr routine can complete interrupt-driven I/O operations.
|KeSynchronizeExecution |Synchronizes the execution of a driver-supplied SynchCritSection routine with that of the ISR associated with a set of interrupt objects, given a pointer to the interrupt objects.
|KeAcquireInterruptSpinLock |Acquires the spin lock that synchronizes access with an interrupt's ISR.
|KeReleaseInterruptSpinLock |Releases the spin lock that synchronized access with an interrupt's ISR.
|KeRegisterNmiCallback |Registers a routine to be called whenever a nonmaskable interrupt (NMI) occurs.
|KeDeregisterNmiCallback |Deregisters a routine registered by KeRegisterNmiCallback.

 
## Driver-Managed Queues
|Function|Description|
|---|---|
|KeInitializeSpinLock |Initializes a variable of type KSPIN_LOCK. An initialized spin lock is a required parameter to the ExInterlockedXxxList routines.
|InitializeListHead |Sets up a queue header for a driver's internal queue, given a pointer to driver-supplied storage for the queue header and queue. An initialized queue header is a required parameter to the ExInterlockedInsert/RemoveXxxList routines.
|ExInterlockedInsertTailList |Inserts an entry at the tail of a doubly linked list, using a spin lock to ensure multiprocessor-safe access to the list and atomic modification of the list links.
|ExInterlockedInsertHeadList |Inserts an entry at the head of a doubly linked list, using a spin lock to ensure multiprocessor-safe access to the list and atomic modification of the links in the list.
|ExInterlockedRemoveHeadList |Removes an entry from the head of a doubly linked list, using a spin lock to ensure multiprocessor-safe access to the list and atomic modification of the links in the list.
|ExInterlockedPopEntryList |Removes an entry from the head of a singly linked list as an atomic operation, using a spin lock to ensure multiprocessor-safe access to the list.
|ExInterlockedPushEntryList |Inserts an entry at the head of a singly linked list as an atomic operation, using a spin lock to ensure multiprocessor-safe access to the list.
|IsListEmpty |Returns TRUE if a queue is empty. (This type of doubly linked list is not protected by a spin lock, unless the caller explicitly manages synchronization to queued entries with an initialized spin lock for which the caller supplies the storage.)
|InsertTailList |Queues an entry at the end of the list.
|InsertHeadList |Queues an entry at the head of the list.
|RemoveHeadList |Dequeues an entry at the head of the list.
|RemoveTailList |Dequeues an entry at the end of the list.
|RemoveEntryList |Returns whether a given entry is in the given list and dequeues the entry if it is.
|PushEntryList |Inserts an entry into the queue. (This type of singly linked list is not protected by a spin lock, unless the caller explicitly manages synchronization to queued entries with an initialized spin lock for which the caller supplies the storage.)
|PopEntryList |Removes an entry from the queue.
|ExInterlockedPopEntrySList |Removes an entry from the head of a sequenced, singly linked list that was set up with ExInitializeSListHead. 
|ExInterlockedPushEntrySList |Queues an entry at the head of a sequenced, singly linked list that was set up with ExInitializeSListHead. 
|ExQueryDepthSList |Returns the number of entries currently queued in a sequenced, singly linked list. 
|ExInitializeNPagedLookasideList |Sets up a lookaside list, protected by a system-supplied spin lock, in nonpaged pool from which the driver can allocate and free blocks of a fixed size. 
|KeInitializeDeviceQueue |Initializes a device queue object to a not-busy state, setting up an associated spin lock for multiprocessor-safe access to device queue entries.
|KeInsertDeviceQueue |Acquires the device queue spin lock and queues an entry to a device driver if the device queue is not empty; otherwise, inserts the entry at the tail of the device queue.
|KeInsertByKeyDeviceQueue |Acquires the device queue spin lock and queues an entry to a device driver if the device queue is not empty; otherwise, inserts the entry into the queue according to the given sort-key value.
|KeRemoveDeviceQueue |Removes an entry from the head of a given device queue.
|KeRemoveByKeyDeviceQueue |Removes an entry, selected according to the specified sort-key value, from the given device queue.
|KeRemoveEntryDeviceQueue |Determines whether a given entry is in the given device queue and, if so, dequeues the entry.

## Driver System Processes and Threads


|Function|Description|
|---|---|
|PsCreateSystemThread |Creates a kernel-mode thread associated with a given process object or with the default system process. Returns a handle for the thread.
|PsTerminateSystemThread |Terminates the current thread and satisfies as many waits as possible for the current thread object.
|PsGetCurrentThread |Returns a handle for the current thread.
|KeGetCurrentThread |Returns a pointer to the opaque thread object that represents the current thread. 
|KeQueryPriorityThread |Returns the current priority of a given thread. 
|KeSetBasePriorityThread |Sets up the run-time priority, relative to the system process, for a driver-created thread.
|KeSetPriorityThread |Sets up the run-time priority for a driver-created thread with a real-time priority attribute.
|KeDelayExecutionThread |Puts the current thread into an alertable or nonalertable wait state for a given interval.
|IoQueueWorkItem |Queues an initialized work queue item so the driver-supplied routine will be called when a system worker thread is given control.
|ZwSetInformationThread |Sets the priority of a given thread for which the caller has a handle.

|Function|Description|
|---|---| 
|PsGetCurrentProcessId| The PsGetCurrentProcessId routine identifies the current thread's process. 
|PsGetProcessCreateTimeQuadPart|The PsGetProcessCreateTimeQuadPart routine returns a LONGLONG value that represents the time at which the process was created. 
|PsGetProcessId| The PsGetProcessId routine returns the process identifier (process ID) that is associated with a specified process. 
|PsQueryTotalCycleTimeProcess| The PsQueryTotalCycleTimeProcess routine returns the accumulated cycle time for the specified process.
|PCREATE_PROCESS_NOTIFY_ROUTINE| Process-creation callback implemented by a driver to track the system-wide creation and deletion of processes against the driver's internal state.
|PsSetCreateProcessNotifyRoutine| The PsSetCreateProcessNotifyRoutine routine adds a driver-supplied callback routine to, or removes it from, a list of routines to be called whenever a process is created or deleted.
|PCREATE_PROCESS_NOTIFY_ROUTINE_EX| A callback routine implemented by a driver to notify the caller when a process is created or exits.
|PsSetCreateProcessNotifyRoutineEx| The PsSetCreateProcessNotifyRoutineEx routine registers or removes a callback routine that notifies the caller when a process is created or exits.
|PsSetCreateProcessNotifyRoutineEx2| The PsSetCreateProcessNotifyRoutineEx2 routine registers or removes a callback routine that notifies the caller when a process is created or deleted.

|Function|Description|
|---|---| 
|PLOAD_IMAGE_NOTIFY_ROUTINE| Called by the operating system to notify the driver when a driver image or a user image (for example, a DLL or EXE) is mapped into virtual memory. 
|PsSetLoadImageNotifyRoutine| The PsSetLoadImageNotifyRoutine routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).
|PsSetLoadImageNotifyRoutineEx| The PsSetLoadImageNotifyRoutineEx routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).
|PsTerminateSystemThread| The PsTerminateSystemThread routine terminates the current system thread.
 

 
### Best practices for implementing process and thread-related callback functions
This set of guidelines applies to these callback routines:

-   PCREATE_PROCESS_NOTIFY_ROUTINE 
-   PCREATE_PROCESS_NOTIFY_ROUTINE_EX 
-   PCREATE_THREAD_NOTIFY_ROUTINE 
-   PLOAD_IMAGE_NOTIFY_ROUTINE 

Keep notify routines short and simple. 
-   Do not make calls into a user mode service to validate the process, thread, or image. 
-   Do not make registry calls. 
-   Do not make blocking and/or Interprocess Communication (IPC) function calls. 
-   Do not synchronize with other threads because it can lead to reentrancy deadlocks. 
-   Use System Worker Threads to queue work especially work involving: 

    -   Slow API’s or API’s that call into other process. 
    -   Any blocking behavior which could interrupt threads in core services. 

-   Be considerate of best practices for kernel mode stack usage. For examples, see How do I keep my driver from running out of kernel-mode stack? and Key Driver Concepts and Tips. 
      


## Run-Time Library (RTL) Routines
For information about functions that copy, concatenate, and format strings in a manner that prevents buffer overrun errors, see [Safe String Functions](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_kernel/#safe-string-functions-for-unicode-and-ansi-characters), below. Other string manipulation functions include the following:

|Function|Description|
|---|---|
|RtlInitString |Initializes the specified string in a buffer.
|RtlInitAnsiString |Initializes the specified ANSI string in a buffer.
|RtlInitUnicodeString |Initializes the specified Unicode string in a buffer.
|RtlAnsiStringToUnicodeSize |Returns the size in bytes required to hold a Unicode version of a given buffered ANSI string.
|RtlAnsiStringToUnicodeString |Converts a buffered ANSI string to a Unicode string, given a pointer to the source-string buffer and the address of caller-supplied storage for a pointer to the destination buffer. (This routine allocates a destination buffer if the caller does not supply the storage.) You can also use the string manipulation routines provided by a compiler to convert ANSI strings to Unicode. 
|RtlFreeUnicodeString |Releases a buffer containing a Unicode string, given a pointer to the buffer returned by RtlAnsiStringToUnicodeString.
|RtlUnicodeStringToAnsiString |Converts a buffered Unicode string to an ANSI string, given a pointer to the source-string buffer and the address of caller-supplied storage for a pointer to the destination buffer. (This routine allocates a destination buffer if the caller does not supply the storage.)
|RtlFreeAnsiString |Releases a buffer containing an ANSI string, given a pointer to the buffer returned by RtlUnicodeStringToAnsiString.
|RtlAppendUnicodeStringToString |Concatenates a copy of a buffered Unicode string with a buffered Unicode string, given pointers to both buffers.
|RtlAppendUnicodeToString |Concatenates a given input string with a buffered Unicode string, given a pointer to the buffer.
|RtlCopyString |Copies the source string to the destination, given pointers to both buffers, or sets the length of the destination string (but not the length of the destination buffer) to zero if the optional pointer to the source-string buffer is NULL.
|RtlCopyUnicodeString |Copies the source string to the destination, given pointers to both buffers, or sets the length of the destination string (but not the length of the destination buffer) to zero if the optional pointer to the source-string buffer is NULL.
|RtlEqualString |Returns TRUE if the given ANSI alphabetic strings are equivalent.
|RtlEqualUnicodeString |Returns TRUE if the given buffered strings are equivalent.
|RtlCompareString |Compares two buffered, single-byte character strings and returns a signed value indicating whether they are equivalent or which is greater. 
|RtlCompareUnicodeString |Compares two buffered Unicode strings and returns a signed value indicating whether they are equivalent or which is greater.
|RtlUpperString |Converts a copy of a buffered string to uppercase and stores the copy in a destination buffer.
|RtlUpcaseUnicodeString |Converts a copy of a buffered Unicode string to uppercase and stores the copy in a destination buffer.
|RtlIntegerToUnicodeString |Converts an unsigned integer value in the specified base to one or more Unicode characters in a buffer.
|RtlUnicodeStringToInteger |RtlUnicodeStringToInteger converts the Unicode string representation of an integer into its integer equivalent.

The following routines are reserved for system use. Do not use them in your driver.

|Routine|Replacement|
|---|---|
|RtlAssert| Use ASSERT instead. |
|RtlGetCallersAddress| Use the intrinsic _ReturnAddress instead. |
|RtlInterlockedAndBits| Use InterlockedAnd instead.|
|RtlInterlockedAndBitsDiscardReturn| Use InterlockedAnd instead.|
|RtlInterlockedClearBits| Use InterlockedAnd instead.|
|RtlInterlockedClearBitsDiscardReturn| Use InterlockedAnd instead.|
|RtlInterlockedSetBits| Use InterlockedOr instead.|
|RtlInterlockedSetBitsDiscardReturn| Use InterlockedOr instead.|
|RtlInterlockedSetClearBits||
|RtlInterlockedXorBits| Use InterlockedXor instead|
|RtlWalkFrameChain||


### Safe String Functions for Unicode and ANSI Characters
Use the functions in this section to manipulate Unicode and ANSI strings in kernel-mode drivers.

Each function is available in two versions:

A W-suffixed version that supports two-byte Unicode characters.

An A-suffixed version that supports one-byte ANSI characters.

If you use the safe string functions instead of the string manipulation functions that are provided by C-language run-time libraries, you protect your code from buffer overrun errors that can make code untrustworthy. For more information, see [Using Safe String Functions](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions).

|Function|Description|
|---|---|
|RtlStringCbCatW| The RtlStringCbCatW and RtlStringCbCatA functions concatenate two byte-counted strings.
|RtlStringCbCatExW| The RtlStringCbCatExW and RtlStringCbCatExA functions concatenate two byte-counted strings. 
|RtlStringCbCatNW| The RtlStringCbCatNW and RtlStringCbCatNA functions concatenate two byte-counted strings while limiting the size of the appended string. 
|RtlStringCbCatNExW| The RtlStringCbCatNExW and RtlStringCbCatNExA functions concatenate two byte-counted strings while limiting the size of the appended string. 
|RtlStringCbCopyW| The RtlStringCbCopyW and RtlStringCbCopyA functions copy a byte-counted string into a buffer. 
|RtlStringCbCopyExW| The RtlStringCbCopyExW and RtlStringCbCopyExA functions copy a byte-counted string into a buffer.
|RtlStringCbCopyNW| The RtlStringCbCopyNW and RtlStringCbCopyNA functions copy a byte-counted string to a buffer while limiting the size of the copied string.
|RtlStringCbCopyNExW| The RtlStringCbCopyNExW and RtlStringCbCopyNExA functions copy a byte-counted string to a buffer while limiting the size of the copied string.
|RtlStringCbLengthW| The RtlStringCbLengthW and RtlStringCbLengthA functions determine the length, in bytes, of a supplied string. 
|RtlStringCbPrintfW| The RtlStringCbPrintfW and RtlStringCbPrintfA functions create a byte-counted text string, with formatting that is based on supplied formatting information. 
|RtlStringCbPrintfExW| The RtlStringCbPrintfExW and RtlStringCbPrintfExA functions create a byte-counted text string, with formatting that is based on supplied formatting information.
|RtlStringCbVPrintfW| The RtlStringCbVPrintfW and RtlStringCbVPrintfA functions create a byte-counted text string, with formatting that is based on supplied formatting information.
|RtlStringCbVPrintfExW| The RtlStringCbVPrintfExW and RtlStringCbVPrintfExA functions create a byte-counted text string, with formatting that is based on supplied formatting information.
|RtlStringCchCatW| The RtlStringCchCatW and RtlStringCchCatA functions concatenate two character-counted strings.
|RtlStringCchCatExW| The RtlStringCchCatExW and RtlStringCchCatExA functions concatenate two character-counted strings.
|RtlStringCchCatNW| The RtlStringCchCatNW and RtlStringCchCatNA functions concatenate two character-counted strings while limiting the size of the appended string. 
|RtlStringCchCatNExW| The RtlStringCchCatNExW and RtlStringCchCatNExA functions concatenate two character-counted strings while limiting the size of the appended string.
|RtlStringCchCopyW| The RtlStringCchCopyW and RtlStringCchCopyA functions copy a null-terminated source string into a destination buffer of specified length. 
|RtlStringCchCopyExW| The RtlStringCchCopyExW and RtlStringCchCopyExA functions copy a character-counted string into a buffer.
|RtlStringCchCopyNW| The RtlStringCchCopyNW and RtlStringCchCopyNA functions copy a character-counted string to a buffer while limiting the size of the copied string.
|RtlStringCchCopyNExW| The RtlStringCchCopyNExW and RtlStringCchCopyNExA functions copy a character-counted string to a buffer while limiting the size of the copied string.
|RtlStringCchLengthW| The RtlStringCchLengthW and RtlStringCchLengthA functions determine the length, in characters, of a supplied string. 
|RtlStringCchPrintfW| The RtlStringCchPrintfW and RtlStringCchPrintfA functions create a character-counted text string, with formatting that is based on supplied formatting information.
|RtlStringCchPrintfExW| The RtlStringCchPrintfExW and RtlStringCchPrintfExA functions create a character-counted text string, with formatting that is based on supplied formatting information.
|RtlStringCchVPrintfW| The RtlStringCchVPrintfW and RtlStringCchVPrintfA functions create a character-counted text string, with formatting that is based on supplied formatting information.
|RtlStringCchVPrintfExW|The RtlStringCchVPrintfExW and RtlStringCchVPrintfExA functions create a character-counted text string, with formatting that is based on supplied formatting information.
|RtlUnalignedStringCbLength| The RtlUnalignedStringCbLengthW function is a version of the RtlStringCbLength function that accepts an unaligned pointer to a string of Unicode characters.
|RtlUnalignedStringCchLengthW| The RtlUnalignedStringCchLengthW function is a version of the RtlStringCchLength function that accepts an unaligned pointer to a string of Unicode characters.
 
### Safe String Functions for UNICODE_STRING Structures
Use the functions in this section to manipulate strings within UNICODE_STRING structures in kernel-mode drivers.

If you use the safe string functions instead of the string manipulation functions that C-language run-time libraries provide, you protect your code from buffer overrun errors that can make code untrustworthy. For more information about safe string functions, see [Using Safe String Functions](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-safe-string-functions).

|Function|Description|
|---|---|
|RtlStringCbCopyUnicodeString| The RtlStringCbCopyUnicodeString function copies the contents of a UNICODE_STRING structure to a specified destination.
|RtlStringCbCopyUnicodeStringEx| The RtlStringCbCopyUnicodeStringEx function copies the contents of a UNICODE_STRING structure to a specified destination. 
|RtlStringCchCopyUnicodeString| The RtlStringCchCopyUnicodeString function copies the contents of a UNICODE_STRING structure to a specified destination.
|RtlStringCchCopyUnicodeStringEx| The RtlStringCchCopyUnicodeStringEx function copies the contents of a UNICODE_STRING structure to a specified destination. 
|RtlUnicodeStringCat| The RtlUnicodeStringCat function concatenates two strings that are contained in UNICODE_STRING structures.
|RtlUnicodeStringCatEx| The RtlUnicodeStringCatEx function concatenates two strings that are contained in UNICODE_STRING structures. 
|RtlUnicodeStringCatString| The RtlUnicodeStringCatString function concatenates two strings when the destination string is contained in a UNICODE_STRING structure.
|RtlUnicodeStringCatStringEx| The RtlUnicodeStringCatStringEx function concatenates two strings when the destination string is contained in a UNICODE_STRING structure.
|RtlUnicodeStringCbCatN| The RtlUnicodeStringCbCatN function concatenates two strings that are contained in UNICODE_STRING structures while limiting the size of the copied string.
|RtlUnicodeStringCbCatNEx| The RtlUnicodeStringCbCatNEx function concatenates two strings that are contained in UNICODE_STRING structures while limiting the size of the copied string.
|RtlUnicodeStringCbCatStringN| The RtlUnicodeStringCbCatStringN function concatenates two strings when the destination string is contained in a UNICODE_STRING structure, while limiting the size of the appended string.
|RtlUnicodeStringCbCatStringNEx| The RtlUnicodeStringCbCatStringNEx function concatenates two strings when the destination string is contained in a UNICODE_STRING structure, while limiting the size of the appended string.
|RtlUnicodeStringCbCopyN| The RtlUnicodeStringCbCopyN function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string.
|RtlUnicodeStringCbCopyNEx| The RtlUnicodeStringCbCopyNEx function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string.
|RtlUnicodeStringCbCopyStringN| The RtlUnicodeStringCbCopyStringN function copies a string into a UNICODE_STRING structure while limiting the size of the copied string.
|RtlUnicodeStringCbCopyStringNEx| The RtlUnicodeStringCbCopyStringNEx function copies a string into a UNICODE_STRING structure while limiting the size of the copied string.
|RtlUnicodeStringCchCatN| The RtlUnicodeStringCchCatN function concatenates two strings that are contained in UNICODE_STRING structures while limiting the size of the copied string.
|RtlUnicodeStringCchCatNEx| The RtlUnicodeStringCchCatNEx function concatenates two strings that are contained in UNICODE_STRING structures while limiting the size of the copied string.
|RtlUnicodeStringCchCatStringN| The RtlUnicodeStringCchCatStringN function concatenates two strings when the destination string is contained in a UNICODE_STRING structure, while limiting the size of the appended string.
|RtlUnicodeStringCchCatStringNEx| The RtlUnicodeStringCchCatStringNEx function concatenates two strings when the destination string is contained in a UNICODE_STRING structure, while limiting the size of the appended string.
|RtlUnicodeStringCchCopyN| The RtlUnicodeStringCchCopyN function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string.
|RtlUnicodeStringCchCopyNEx| The RtlUnicodeStringCchCopyNEx function copies a string from one UNICODE_STRING structure to another while limiting the size of the copied string.
|RtlUnicodeStringCchCopyStringN| The RtlUnicodeStringCchCopyStringN function copies a string into a UNICODE_STRING structure while limiting the size of the copied string.
|RtlUnicodeStringCchCopyStringNEx| The RtlUnicodeStringCchCopyStringNEx function copies a string into a UNICODE_STRING structure while limiting the size of the copied string.
|RtlUnicodeStringCopy| The RtlUnicodeStringCopy function copies a string from one UNICODE_STRING structure to another.
|RtlUnicodeStringCopyEx| The RtlUnicodeStringCopyEx function copies a string from one UNICODE_STRING structure to another.
|RtlUnicodeStringCopyString| The RtlUnicodeStringCopyString function copies a string into a UNICODE_STRING structure.
|RtlUnicodeStringCopyStringEx| The RtlUnicodeStringCopyStringEx function copies a string into a UNICODE_STRING structure.
|RtlUnicodeStringInit| The RtlUnicodeStringInit function initializes a UNICODE_STRING structure.
|RtlUnicodeStringInitEx| The RtlUnicodeStringInitEx function initializes a UNICODE_STRING structure.
|RtlUnicodeStringPrintf| The RtlUnicodeStringPrintf function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure.
|RtlUnicodeStringPrintfEx| The RtlUnicodeStringPrintfEx function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure.
|RtlUnicodeStringValidate| The RtlUnicodeStringValidate function validates the contents of a UNICODE_STRING structure.
|RtlUnicodeStringValidateEx| The RtlUnicodeStringValidateEx function validates the contents of a UNICODE_STRING structure.
|RtlUnicodeStringVPrintf| The RtlUnicodeStringVPrintf function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure.
|RtlUnicodeStringVPrintfEx| The RtlUnicodeStringVPrintfEx function creates a text string, with formatting that is based on supplied formatting information, and stores the string in a UNICODE_STRING structure.

## Safe Integer Library Routines
This section describes the safe integer functions for drivers. These functions are defined as inline functions in the Ntintsafe.h header file in the WDK. The safe integer functions are designed to help drivers to avoid arithmetic overflow errors. These functions are divided into two sets; the first converts integer values from one type to another, and the second performs math functions. For more information about these functions, see Using Safe Integer Functions.

The Intsafe.h header file in the Windows SDK defines a similar set of safe integer functions for use by applications. For more information about this version of the safe integer functions, see Intsafe.h Functions.


 
## Data Conversions
|Function|Description|
|---|---|
|InterlockedExchange |Sets a variable of type LONG to a given value as an atomic operation; returns the original value of the variable.
|RtlConvertLongToLargeInteger |Converts a given LONG value to a LARGE_INTEGER value.
|RtlConvertUlongToLargeInteger |Converts a given ULONG value to a LARGE_INTEGER value.
|RtlTimeFieldsToTime |Converts information in a TIME_FIELDS structure to system time.
|RtlTimeToTimeFields |Converts a system time value into a buffered TIME_FIELDS value.
|ExSystemTimeToLocalTime |Adds the time-zone bias for the current locale to GMT system time, converting it to local time.
|ExLocalTimeToSystemTime |Subtracts the time-zone bias from the local time, converting it to GMT system time.
|RtlAnsiStringToUnicodeString |Converts a buffered ANSI string to a Unicode string, given a pointer to the source-string buffer and the address of caller-supplied storage for a pointer to the destination buffer. (This routine allocates a destination buffer if the caller does not supply the storage.)
|RtlUnicodeStringToAnsiString |Converts a buffered Unicode string to an ANSI string, given a pointer to the source-string buffer and the address of caller-supplied storage for a pointer to the destination buffer. (This routine allocates a destination buffer if the caller does not supply the storage.)
|RtlUpperString |Converts a copy of a buffered string to uppercase and stores the copy in a destination buffer.
|RtlUpcaseUnicodeString |Converts a copy of a buffered Unicode string to uppercase and stores the copy in a destination buffer.
|RtlCharToInteger |Converts a single-byte character value into an integer in the specified base. 
|RtlIntegerToUnicodeString |Converts an unsigned integer value in the specified base to one or more Unicode characters in the given buffer.
|RtlUnicodeStringToInteger |Converts a Unicode string representation of an integer into its integer equivalent.

## Access to Driver-Managed Objects
|Function|Description|
|---|---|
|ExCreateCallback |Creates or opens a callback object.
|ExNotifyCallback |Calls the callback routines registered with a previously created or opened callback object. 
|ExRegisterCallback |Registers a callback routine with a previously created or opened callback object, so that the caller can be notified when conditions defined for the callback routine occur.
|ExUnregisterCallback |Cancels the registration of a callback routine with a callback object.
|IoRegisterDeviceInterface |Registers device functionality (a device interface) that a driver can enable for use by applications or other system components.
|IoSetDeviceInterfaceState |Enables or disables a previously registered device interface. Applications and other system components can open only interfaces that are enabled.
|IoGetDeviceInterfaceAlias |Returns the alias device interface of the specified interface class, if the alias exists. Device interfaces are considered aliases if they are exposed by the same underlying device and have identical interface reference strings, but are of different interface classes.
|IoGetDeviceInterfaces |Returns a list of device interfaces of a particular device interface class (such as all devices on the system that support a HID interface).
|IoGetFileObjectGenericMapping |Returns information about the mapping between generic access rights and specific access rights for file objects.
|IoSetShareAccess |Sets the access allowed to a given file object representing a device. (Only highest-level drivers can call this routine.)
|IoCheckShareAccess |Checks whether a request to open a file object specifies a desired access that is compatible with the current shared access permissions for the open file object. (Only highest-level drivers can call this routine.)
|IoUpdateShareAccess |Modifies the current shared access permissions on the given file object. (Only highest-level drivers can call this routine.)
|IoRemoveShareAccess |Restores the shared access permissions on the given file object that were modified by a preceding call to IoUpdateShareAccess.
|RtlLengthSecurityDescriptor |Returns the size in bytes of a given security descriptor.
|RtlValidSecurityDescriptor |Returns whether a given security descriptor is valid.
|RtlCreateSecurityDescriptor |Initializes a new security descriptor to an absolute format with default values (in effect, with no security constraints).
|RtlSetDaclSecurityDescriptor |Sets the discretionary ACL information for a given security descriptor in absolute format.
|SeAssignSecurity |Builds a security descriptor for a new object, given the security descriptor of its parent directory (if any) and an originally requested security for the object.
|SeDeassignSecurity |Deallocates the memory associated with a security descriptor that was created with SeAssignSecurity.
|SeValidSecurityDescriptor |Returns whether a given security descriptor is structurally valid. 
|SeAccessCheck |Returns a Boolean value indicating whether the requested access rights can be granted to an object protected by a security descriptor and, possibly, a current owner.
|SeSinglePrivilegeCheck |Returns a Boolean value indicating whether the current thread has at least the given privilege level.

 
## Error Handling
|Function|Description|
|---|---|
|IoAllocateErrorLogEntry |Allocates and initializes an error log packet; returns a pointer so the caller can supply error log data and call IoWriteErrorLogEntry with the packet.
|IoFreeErrorLogEntry |Frees an error log entry allocated by IoAllocateErrorLogEntry.
|IoWriteErrorLogEntry |Queues a previously allocated error log packet, filled in by the driver, to the system error logging thread.
|IoIsErrorUserInduced |Returns a Boolean value indicating whether an I/O request failed due to one of the following (user-correctable) conditions: STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_UNRECOGNIZED_MEDIA, STATUS_VERIFY_REQUIRED, STATUS_WRONG_VOLUME, STATUS_MEDIA_WRITE_PROTECTED, or STATUS_NO_MEDIA_IN_DEVICE. If the result is TRUE, a removable-media driver must call IoSetHardErrorOrVerifyDevice before completing the IRP.
|IoSetHardErrorOrVerifyDevice |Supplies the device object for which the given IRP was failed due to a user-induced error, such as supplying the incorrect media for the requested operation or changing the media before the requested operation was completed. (A file system driver uses the associated device object to send a dialog box to the user; the user can then correct the error or retry the operation.)
|IoSetThreadHardErrorMode |Enables or disables error reporting for the current thread using IoRaiseHardError or IoRaiseInformationalHardError.
|IoRaiseHardError |Causes a dialog box to be sent to the user indicating that the given IRP was failed on the given device object for an optional VPB, so that the user can correct the error or retry the operation.
|IoRaiseInformationalHardError |Causes a dialog box to be sent to the user, showing an I/O error status and optional string supplying more information.
|ExRaiseStatus |Raises an error status so that a caller-supplied structured exception handler is called. (This routine is useful only to highest-level drivers that supply exception handlers, in particular to file systems.)
|KeBugCheckEx |Brings down the system in a controlled manner, displaying the bug-check code and possibly more information, after the caller discovers an unrecoverable inconsistency that will corrupt the system unless it is brought down. After the system is brought down, this routine displays bug-check and possibly other information. (This routine can be called when debugging under-development drivers. Otherwise, drivers should never call this routine when they can handle an error by failing an IRP and by calling IoAllocateErrorLogEntry and IoWriteErrorLogEntry.)
|KeBugCheck |Brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that will corrupt the system if the caller continues to run. KeBugCheckEx is preferable.
|KeInitializeCallbackRecord |Initializes a bug-check callback record before a device driver calls KeRegisterBugCheckCallback. 
|KeRegisterBugCheckCallback |Registers the device driver's bug-check callback routine, which is called if a system bug check occurs. Such a driver-supplied routine saves driver-determined state information, such as the contents of device registers, that would not otherwise be written into the system crash-dump file. 
|KeDeregisterBugCheckCallback |Removes a device driver's callback routine from the set of registered bug-check callback routines. 

