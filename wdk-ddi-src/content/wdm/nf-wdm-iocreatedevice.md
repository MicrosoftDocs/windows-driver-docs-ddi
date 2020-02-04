---
UID: NF:wdm.IoCreateDevice
title: IoCreateDevice function (wdm.h)
description: The IoCreateDevice routine creates a device object for use by a driver.
old-location: kernel\iocreatedevice.htm
tech.root: kernel
ms.assetid: 54ca9dc8-8095-4b62-9ebc-f297abb429ca
ms.date: 04/30/2018
ms.keywords: IoCreateDevice, IoCreateDevice routine [Kernel-Mode Driver Architecture], k104_1e38a631-7e65-4b4b-8d51-3150a8073511.xml, kernel.iocreatedevice, wdm/IoCreateDevice
f1_keywords:
 - "wdm/IoCreateDevice"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: AddDevice, CheckDeviceObjectFlags, IrqlIoPassive1, MiniportOnlyWdmDevice, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoCreateDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCreateDevice function

## -description

The **IoCreateDevice** routine creates a device object for use by a driver.

## -parameters

### -param DriverObject [in]

Pointer to the driver object for the caller. Each driver receives a pointer to its driver object in a parameter to its [DriverEntry](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_initialize) routine. WDM function and filter drivers also receive a driver object pointer in their [AddDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device) routines.

### -param DeviceExtensionSize [in]

Specifies the driver-determined number of bytes to be allocated for the [device extension](https://docs.microsoft.com/windows-hardware/drivers/kernel/device-extensions) of the device object. The internal structure of the device extension is driver-defined.

### -param DeviceName [in, optional]

Optionally points to a buffer containing a null-terminated Unicode string that names the device object. The string must be a full path name. WDM filter and function drivers do not name their device objects. For more information, see [Named Device Objects](https://docs.microsoft.com/windows-hardware/drivers/kernel/named-device-objects).

> [!ALERT]
> If a device name is not supplied (that is, *DeviceName* is **NULL**), the device object created by **IoCreateDevice** will not (and cannot) have a discretionary access control list (DACL) associated with it. For additional information, see [Security Descriptors](https://docs.microsoft.com/windows-hardware/drivers/kernel/security-descriptors).

### -param DeviceType [in]

Specifies one of the system-defined FILE_DEVICE_*XXX* constants that indicate the type of device (such as FILE_DEVICE_DISK or FILE_DEVICE_KEYBOARD) or a vendor-defined value for a new type of device. For more information, see [Specifying Device Types](https://docs.microsoft.com/windows-hardware/drivers/kernel/specifying-device-types).

### -param DeviceCharacteristics [in]

Specifies one or more system-defined constants, ORed together, that provide additional information about the driver's device. For a list of possible device characteristics, see [DEVICE_OBJECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object). For more information about how to specify device characteristics, see [Specifying Device Characteristics](https://docs.microsoft.com/windows-hardware/drivers/kernel/specifying-device-characteristics). Most drivers specify FILE_DEVICE_SECURE_OPEN for this parameter.

### -param Exclusive [in]

Specifies if the device object represents an [exclusive device](https://docs.microsoft.com/windows-hardware/drivers/). Most drivers set this value to **FALSE**. For more information about exclusive access, see [Specifying Exclusive Access to Device Objects](https://docs.microsoft.com/windows-hardware/drivers/kernel/specifying-exclusive-access-to-device-objects).

### -param DeviceObject [out]

Pointer to a variable that receives a pointer to the newly created [DEVICE_OBJECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object) structure. The **DEVICE_OBJECT** structure is allocated from nonpaged pool.

## -returns

**IoCreateDevice** returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. A partial list of the failure codes returned by this function includes:

- **STATUS_INSUFFICIENT_RESOURCES**

- **STATUS_OBJECT_NAME_COLLISION**

## -remarks

**IoCreateDevice** creates a device object and returns a pointer to the object. The caller is responsible for deleting the object when it is no longer needed by calling [IoDeleteDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodeletedevice).

**IoCreateDevice** can only be used to create an unnamed device object, or a named device object for which a security descriptor is set by an INF file. Otherwise, drivers must use [IoCreateDeviceSecure](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdmsec/nf-wdmsec-wdmlibiocreatedevicesecure) to create named device objects. For more information, see [Creating a Device Object](https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-device-object). The caller is responsible for setting certain members of the returned device object. For more information, see [Initializing a Device Object](https://docs.microsoft.com/windows-hardware/drivers/kernel/initializing-a-device-object) and the device-type-specific documentation for your device.

Be careful to specify the *DeviceType* and *DeviceCharacteristics* values in the correct parameters. Both parameters use system-defined FILE_*XXX* constants and some driver writers specify the values in the wrong parameters by mistake.

A remote file system that creates a named device object for a network redirector, and that registers using [FsRtlRegisterUncProvider](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlregisteruncprovider), must specify FILE_REMOTE_DEVICE as one of the options in the *DeviceCharacteristics* parameter of **IoCreateDevice**.

Device objects for disks, tapes, CD-ROMs, and RAM disks are given a Volume Parameter Block (VPB) that is initialized to indicate that the volume has never been mounted on the device.

If a driver's call to **IoCreateDevice** returns an error, the driver should release any resources that it allocated for that device.

## -see-also

[DEVICE_OBJECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object)

[FsRtlRegisterUncProvider](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlregisteruncprovider)

[IoAttachDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevice)

[IoAttachDeviceToDeviceStack](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevicetodevicestack)

[IoCreateDeviceSecure](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdmsec/nf-wdmsec-wdmlibiocreatedevicesecure)

[IoCreateSymbolicLink](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatesymboliclink)

[IoDeleteDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodeletedevice)
