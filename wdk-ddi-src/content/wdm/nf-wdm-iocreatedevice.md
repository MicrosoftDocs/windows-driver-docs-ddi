---
UID: NF:wdm.IoCreateDevice
title: IoCreateDevice function (wdm.h)
description: The IoCreateDevice routine creates a device object for use by a driver.
old-location: kernel\iocreatedevice.htm
tech.root: kernel
ms.assetid: 54ca9dc8-8095-4b62-9ebc-f297abb429ca
ms.date: 04/30/2018
ms.keywords: IoCreateDevice, IoCreateDevice routine [Kernel-Mode Driver Architecture], k104_1e38a631-7e65-4b4b-8d51-3150a8073511.xml, kernel.iocreatedevice, wdm/IoCreateDevice
ms.topic: function
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
req.irql: "<= APC_LEVEL"
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

Pointer to the driver object for the caller. Each driver receives a pointer to its driver object in a parameter to its [DriverEntry](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_initialize) routine. WDM function and filter drivers also receive a driver object pointer in their [AddDevice](https://msdn.microsoft.com/library/windows/hardware/ff540521) routines.

### -param DeviceExtensionSize [in]

Specifies the driver-determined number of bytes to be allocated for the [device extension](https://msdn.microsoft.com/9ea59994-1112-4ae5-96a8-fa0670694b53) of the device object. The internal structure of the device extension is driver-defined.

### -param DeviceName [in, optional]

Optionally points to a buffer containing a null-terminated Unicode string that names the device object. The string must be a full path name. WDM filter and function drivers do not name their device objects. For more information, see [Named Device Objects](https://msdn.microsoft.com/library/windows/hardware/ff556420).

> [!ALERT]
> If a device name is not supplied (that is, *DeviceName* is **NULL**), the device object created by **IoCreateDevice** will not (and cannot) have a discretionary access control list (DACL) associated with it. For additional information, see [Security Descriptors](https://msdn.microsoft.com/library/windows/hardware/ff563698).

### -param DeviceType [in]

Specifies one of the system-defined FILE_DEVICE_*XXX* constants that indicate the type of device (such as FILE_DEVICE_DISK or FILE_DEVICE_KEYBOARD) or a vendor-defined value for a new type of device. For more information, see [Specifying Device Types](https://msdn.microsoft.com/library/windows/hardware/ff563821).

### -param DeviceCharacteristics [in]

Specifies one or more system-defined constants, ORed together, that provide additional information about the driver's device. For a list of possible device characteristics, see [DEVICE_OBJECT](https://msdn.microsoft.com/library/windows/hardware/ff543147). For more information about how to specify device characteristics, see [Specifying Device Characteristics](https://msdn.microsoft.com/library/windows/hardware/ff563818). Most drivers specify FILE_DEVICE_SECURE_OPEN for this parameter.

### -param Exclusive [in]

Specifies if the device object represents an [exclusive device](https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab). Most drivers set this value to **FALSE**. For more information about exclusive access, see [Specifying Exclusive Access to Device Objects](https://msdn.microsoft.com/library/windows/hardware/ff563827).

### -param DeviceObject [out]

Pointer to a variable that receives a pointer to the newly created [DEVICE_OBJECT](https://msdn.microsoft.com/library/windows/hardware/ff543147) structure. The **DEVICE_OBJECT** structure is allocated from nonpaged pool.

## -returns

**IoCreateDevice** returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. A partial list of the failure codes returned by this function includes:

- **STATUS_INSUFFICIENT_RESOURCES**

- **STATUS_OBJECT_NAME_COLLISION**

## -remarks

**IoCreateDevice** creates a device object and returns a pointer to the object. The caller is responsible for deleting the object when it is no longer needed by calling [IoDeleteDevice](https://msdn.microsoft.com/library/windows/hardware/ff549083).

**IoCreateDevice** can only be used to create an unnamed device object, or a named device object for which a security descriptor is set by an INF file. Otherwise, drivers must use [IoCreateDeviceSecure](https://msdn.microsoft.com/library/windows/hardware/ff548407) to create named device objects. For more information, see [Creating a Device Object](https://msdn.microsoft.com/library/windows/hardware/ff542862). The caller is responsible for setting certain members of the returned device object. For more information, see [Initializing a Device Object](https://msdn.microsoft.com/library/windows/hardware/ff547807) and the device-type-specific documentation for your device.

Be careful to specify the *DeviceType* and *DeviceCharacteristics* values in the correct parameters. Both parameters use system-defined FILE_*XXX* constants and some driver writers specify the values in the wrong parameters by mistake.

A remote file system that creates a named device object for a network redirector, and that registers using [FsRtlRegisterUncProvider](https://msdn.microsoft.com/library/windows/hardware/ff547178), must specify FILE_REMOTE_DEVICE as one of the options in the *DeviceCharacteristics* parameter of **IoCreateDevice**.

Device objects for disks, tapes, CD-ROMs, and RAM disks are given a Volume Parameter Block (VPB) that is initialized to indicate that the volume has never been mounted on the device.

If a driver's call to **IoCreateDevice** returns an error, the driver should release any resources that it allocated for that device.

## -see-also

[DEVICE_OBJECT](https://msdn.microsoft.com/f3522315-cf15-41f7-ac87-c625c7dc8040)

[FsRtlRegisterUncProvider](https://msdn.microsoft.com/library/windows/hardware/ff547178)

[IoAttachDevice](https://msdn.microsoft.com/library/windows/hardware/ff548294)

[IoAttachDeviceToDeviceStack](https://msdn.microsoft.com/library/windows/hardware/ff548300)

[IoCreateDeviceSecure](https://msdn.microsoft.com/library/windows/hardware/ff548407)

[IoCreateSymbolicLink](https://msdn.microsoft.com/library/windows/hardware/ff549043)

[IoDeleteDevice](https://msdn.microsoft.com/library/windows/hardware/ff549083)
