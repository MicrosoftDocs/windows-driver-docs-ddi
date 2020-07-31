---
UID: NF:wdm.IoOpenDeviceRegistryKey
title: IoOpenDeviceRegistryKey function (wdm.h)
description: The IoOpenDeviceRegistryKey routine returns a handle to a device-specific or a driver-specific registry key for a particular device instance.
old-location: kernel\ioopendeviceregistrykey.htm
tech.root: kernel
ms.assetid: c3b67c73-446b-42a8-bc41-2ca42fde3513
ms.date: 04/30/2018
keywords: ["IoOpenDeviceRegistryKey function"]
ms.keywords: IoOpenDeviceRegistryKey, IoOpenDeviceRegistryKey routine [Kernel-Mode Driver Architecture], k104_7b6ab819-56e3-4d4a-956a-51e4a83300f0.xml, kernel.ioopendeviceregistrykey, wdm/IoOpenDeviceRegistryKey
f1_keywords:
 - "wdm/IoOpenDeviceRegistryKey"
 - "IoOpenDeviceRegistryKey"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoOpenDeviceRegistryKey
targetos: Windows
req.typenames: 
---

# IoOpenDeviceRegistryKey function


## -description


The <b>IoOpenDeviceRegistryKey</b> routine returns a handle to a device-specific or a driver-specific registry key for a particular device instance. 


## -parameters




### -param DeviceObject [in]

Pointer to the PDO of the device instance for which the registry key is to be opened.


### -param DevInstKeyType [in]

Specifies flags indicating whether to open a device-specific hardware key or a driver-specific software key. The flags also indicate whether the key is relative to the current hardware profile. For more information about hardware and software keys, see [Registry Keys for Drivers](https://docs.microsoft.com/windows-hardware/drivers/install/overview-of-registry-trees-and-keys) and [Introduction to Registry Keys for Drivers](https://docs.microsoft.com/windows-hardware/drivers/wdf/introduction-to-registry-keys-for-drivers).

The flags are defined as follows:





#### PLUGPLAY_REGKEY_DEVICE

Open the <b>Device Parameters</b> subkey under the device's hardware key (see [HKLM\SYSTEM\CurrentControlSet\Enum Registry Tree](https://docs.microsoft.com/windows-hardware/drivers/install/hklm-system-currentcontrolset-enum-registry-tree)), a device-specific registry subkey that contains information about the device. The key is located under the key for the device instance specified by *DeviceObject*. This flag cannot be specified with PLUGPLAY_REGKEY_DRIVER.





#### PLUGPLAY_REGKEY_DRIVER

Open a *software key* for storing driver-specific information. This flag cannot be specified with PLUGPLAY_REGKEY_DEVICE.

A driver's software key is also called its *driver key* because the registry contains a software key for each driver. The registry contains a list of all of the device classes, and each driver's software key resides under its device class entry. The system stores information about each driver under its software key. For more information about software keys, see [The HKLM\SYSTEM\CurrentControlSet\Control Tree](https://docs.microsoft.com/windows-hardware/drivers/install/hklm-system-currentcontrolset-control-registry-tree).

#### PLUGPLAY_REGKEY_CURRENT_HWPROFILE

**Note**: Hardware profiles are deprecated and state should not be stored relative to a hardware profile.

Open a key relative to the current hardware profile for device or driver information. This allows the driver to access configuration information that is hardware-profile-specific. The caller must specify either PLUGPLAY_REGKEY_DEVICE or PLUGPLAY_REGKEY_DRIVER with this flag. For more information, see [HKLM\SYSTEM\CurrentControlSet\HardwareProfiles Registry Tree](https://docs.microsoft.com/windows-hardware/drivers/install/hklm-system-currentcontrolset-hardwareprofiles-registry-tree).


### -param DesiredAccess [in]

Specifies the [ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask) value that represents the access the caller needs to the key. See the [ZwCreateKey](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey) routine for a description of each KEY_*XXX* access right.


### -param DeviceRegKey [out]

Pointer to a caller-allocated buffer that, on successful return, contains a handle to the requested registry key. 


## -returns

**IoOpenDeviceRegistryKey** returns STATUS_SUCCESS if the call was successful. Possible error return values include the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Possibly indicates that the caller specified an illegal set of <i>DevInstKeyType</i> flags.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Possibly indicates that the <i>DeviceObject</i> is not a valid PDO.

</td>
</tr>
</table>
 




## -remarks



The driver must call [ZwClose](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwclose) to close the handle returned from this routine when access is no longer required.

The registry keys opened by this routine are nonvolatile.

User-mode setup applications can access these registry keys by using [device installation functions](https://docs.microsoft.com/windows-hardware/drivers/install/using-device-installation-functions) such as [SetupDiOpenDevRegKey](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdiopendevregkey). An example of a user-mode setup applications would be a class installer, a Win32 DLL that performs installation operations for devices in a particular [Device Setup Class](https://docs.microsoft.com/windows-hardware/drivers/install/overview-of-device-setup-classes).

To create registry keys, use <a href="https://docs.microsoft.com/windows-hardware/drivers/install/inf-addreg-directive">INF AddReg directives</a> in an INF file or use [SetupDiCreateDevRegKey](https://docs.microsoft.com/windows/desktop/api/setupapi/nf-setupapi-setupdicreatedevregkeya) in a setup application.

Callers of **IoOpenDeviceRegistryKey** must be running at IRQL = PASSIVE_LEVEL in the context of a system thread. 




## -see-also

[Introduction to Registry Keys for Drivers](https://docs.microsoft.com/windows-hardware/drivers/wdf/introduction-to-registry-keys-for-drivers)

[ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask)

[ZwCreateKey](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey)
 
[ZwClose](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwclose)
 

