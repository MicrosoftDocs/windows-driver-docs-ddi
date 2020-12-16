---
UID: NF:wdm.IoOpenDeviceRegistryKey
title: IoOpenDeviceRegistryKey function (wdm.h)
description: The IoOpenDeviceRegistryKey routine returns a handle to a registry state location for a particular device instance.
old-location: kernel\ioopendeviceregistrykey.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoOpenDeviceRegistryKey function"]
ms.keywords: IoOpenDeviceRegistryKey, IoOpenDeviceRegistryKey routine [Kernel-Mode Driver Architecture], k104_7b6ab819-56e3-4d4a-956a-51e4a83300f0.xml, kernel.ioopendeviceregistrykey, wdm/IoOpenDeviceRegistryKey
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IoOpenDeviceRegistryKey
 - wdm/IoOpenDeviceRegistryKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoOpenDeviceRegistryKey
---

# IoOpenDeviceRegistryKey function


## -description

The <b>IoOpenDeviceRegistryKey</b> routine returns a handle to a registry state location for a particular device instance.

## -parameters

### -param DeviceObject 

[in]
Pointer to the [physical device object (PDO)](/windows-hardware/drivers/kernel/when-are-wdm-device-objects-created-) of the device instance for which the registry state location is to be opened.

### -param DevInstKeyType 

[in]
Specifies flags indicating whether to open a device-specific hardware key or a driver-specific software key. The flags also indicate whether the key is relative to the current hardware profile. For more information about hardware and software keys, see  [Introduction to Registry Keys for Drivers](/windows-hardware/drivers/wdf/introduction-to-registry-keys-for-drivers).

The flags are defined as follows:





#### PLUGPLAY_REGKEY_DEVICE

Open the device's hardware key, a device-specific registry state location that contains information about the device. This flag cannot be specified with PLUGPLAY_REGKEY_DRIVER.





#### PLUGPLAY_REGKEY_DRIVER

Open the device's software key, a device-specific registry state location for storing driver-specific information. This flag cannot be specified with PLUGPLAY_REGKEY_DEVICE.


#### PLUGPLAY_REGKEY_CURRENT_HWPROFILE

**Note**: Hardware profiles are deprecated and state should not be stored relative to a hardware profile.

Open a key relative to the current hardware profile for device or driver information. This allows the driver to access configuration information that is hardware-profile-specific. The caller must specify either PLUGPLAY_REGKEY_DEVICE or PLUGPLAY_REGKEY_DRIVER with this flag. 

### -param DesiredAccess 

[in]
Specifies the [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) value that represents the access the caller needs to the key. See the [ZwCreateKey](./nf-wdm-zwcreatekey.md) routine for a description of each KEY_*XXX* access right.

### -param DeviceRegKey 

[out]
Pointer to a caller-allocated buffer that, on successful return, contains a handle to the requested registry state location.

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

The driver must call [ZwClose](./nf-wdm-zwclose.md) to close the handle returned from this routine when access is no longer required.

The registry keys opened by this routine are nonvolatile.

User-mode setup applications can access these registry keys by using [CM_Open_DevNode_Key](/windows/win32/api/cfgmgr32/nf-cfgmgr32-cm_open_devnode_key) or [device information functions](/windows-hardware/drivers/install/using-device-installation-functions#device-information-functions) such as [SetupDiOpenDevRegKey](/windows/win32/api/setupapi/nf-setupapi-setupdiopendevregkey) or [SetupDiCreateDevRegKey](/windows/win32/api/setupapi/nf-setupapi-setupdicreatedevregkeya).

To pre-populate state in these registry state locations at driver package installation time, use <a href="/windows-hardware/drivers/install/inf-addreg-directive">INF AddReg directives</a> in an INF file.

Callers of **IoOpenDeviceRegistryKey** must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.

## -see-also

[Introduction to Registry Keys for Drivers](/windows-hardware/drivers/wdf/introduction-to-registry-keys-for-drivers)

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[ZwCreateKey](./nf-wdm-zwcreatekey.md)

[ZwClose](./nf-wdm-zwclose.md)

[Device nodes and device stacks](/windows-hardware/drivers/gettingstarted/device-nodes-and-device-stacks)