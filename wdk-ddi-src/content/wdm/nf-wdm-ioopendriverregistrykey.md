---
UID: NF:wdm.IoOpenDriverRegistryKey
title: IoOpenDriverRegistryKey function (wdm.h)
description: Reserved.
ms.assetid: 5166cf0f-81c2-4567-91a8-67ae6727fbdd
ms.date: 10/19/2018
f1_keywords:
 - "wdm/IoOpenDriverRegistryKey"
ms.keywords: IoOpenDriverRegistryKey
req.header: wdm.h
req.include-header: wdm.h, ntddk.h, or ntifs.h
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location:
- NtosKrnl.exe
api_name: 
- IoOpenDriverRegistryKey
product:
- Windows
targetos: Windows

ms.custom: 19H1
---

# IoOpenDriverRegistryKey function


## -description

The **IoOpenDriverRegistryKey** routine returns a handle to a driver-specific registry key for a particular driver.

## -parameters

### -param DriverObject [in]
A pointer to a [**DRIVER_OBJECT**](ns-wdm-_driver_object.md) structure. This structure must be the driver object for the calling driver.

### -param RegKeyType [in]
An enumeration of type [**DRIVER_REGKEY_TYPE**](ne-wdm-driver_regkey_type.md) that indicates the type of the requested registry key.

### -param DesiredAccess [in]
Specifies the [ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask) value that represents the access rights needed for the key. See [**ZwCreateKey**](nf-wdm-zwcreatekey.md) for a description of each KEY_XXX access right.

### -param Flags [in]
Set to zero.

### -param DriverRegKey [out]
A pointer to the HANDLE variable that, on successful return, contains a handle to the requested registry key.

## -returns
**IoOpenDriverRegistryKey** returns STATUS_SUCCESS if the call successfully opened a handle to the requested registry key.

## -remarks

The driver must call [**ZwClose**](nf-wdm-zwclose.md) to close the handle returned from this routine when access is no longer needed.

The registry keys opened by this routine are nonvolatile.

To provision keys and values under the immutable **DriverRegKeyParameters** registry key, use an [AddReg directive](https://docs.microsoft.com/windows-hardware/drivers/install/inf-addreg-directive) from a *service-install-section* to reference an *add-registry-section* section that contains entries with a reg-root of `HKR` and a subkey of `Parameters`.

Callers of **IoOpenDriverRegistryKey** must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.


## -see-also

[**ZwClose**](nf-wdm-zwclose.md)	

[ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask)

[**DRIVER_REGKEY_TYPE**](ne-wdm-driver_regkey_type.md)
