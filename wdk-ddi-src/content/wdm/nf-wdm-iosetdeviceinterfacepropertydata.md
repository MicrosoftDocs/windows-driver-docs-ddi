---
UID: NF:wdm.IoSetDeviceInterfacePropertyData
title: IoSetDeviceInterfacePropertyData function (wdm.h)
description: The IoSetDeviceInterfacePropertyData routine modifies the current value of a device interface property.
old-location: kernel\iosetdeviceinterfacepropertydata.htm
tech.root: kernel
ms.date: 04/12/2022
keywords: ["IoSetDeviceInterfacePropertyData function"]
ms.keywords: IoSetDeviceInterfacePropertyData, IoSetDeviceInterfacePropertyData routine [Kernel-Mode Driver Architecture], kernel.iosetdeviceinterfacepropertydata, wdm/IoSetDeviceInterfacePropertyData
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available for Windows 8 and later versions of Windows.
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoSetDeviceInterfacePropertyData
 - wdm/IoSetDeviceInterfacePropertyData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoSetDeviceInterfacePropertyData
---

# IoSetDeviceInterfacePropertyData function

## -description

The **IoSetDeviceInterfacePropertyData** routine modifies the current value of a [device interface property](/windows-hardware/drivers/install/accessing-device-interface-properties).

## -parameters

### -param SymbolicLinkName [in]

A pointer to a string that identifies the device interface instance. This string was obtained from a previous call to the [IoGetDeviceInterfaces](./nf-wdm-iogetdeviceinterfaces.md), [IoGetDeviceInterfaceAlias](./nf-wdm-iogetdeviceinterfacealias.md), or [IoRegisterDeviceInterface](./nf-wdm-ioregisterdeviceinterface.md) routine.

### -param PropertyKey [in]

A pointer to a [DEVPROPKEY](/previous-versions/windows/hardware/drivers/dn315031(v=vs.85)) structure that contains the device interface property key.

### -param Lcid [in]

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to **LOCALE_NEUTRAL**. The **LOCALE_NEUTRAL** LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to **LOCALE_SYSTEM_DEFAULT** or **LOCALE_USER_DEFAULT**. For more information about language-specific LCID values, see [LCID Structure](/openspecs/windows_protocols/ms-lcid/63d3d639-7fd2-4afb-abbe-0d5b5551eef8).

### -param Flags [in]

Set this parameter to **PLUGPLAY_PROPERTY_PERSISTENT** if the property value set by this routine should persist across computer restarts. Otherwise, set *Flags* to zero.

### -param Type [in]

Set this parameter to the [DEVPROPTYPE](/previous-versions/ff543546(v=vs.85)) value that specifies the type of the data that is supplied in the *Data* buffer.

### -param Size [in]

Specifies the size, in bytes, of the buffer that *Data* points to.

### -param Data [in, optional]

A pointer to the device interface property data. Set this parameter to **NULL** to delete the specified property. If *Data* is non-**NULL**, the routine stores an internal copy of the property value. The buffer pointed to by *Data* does not need to remain valid after the call returns.

## -returns

**IoSetDeviceInterfacePropertyData** returns STATUS_SUCCESS if the call was successful. Possible error return values include the following status codes.

| Return code | Description |
|--|--|
| **STATUS_UNSUCCESSFUL** | The specified LCID value is not valid. |
| **STATUS_NOT_IMPLEMENTED** | The specified property is not supported. |

## -remarks

Kernel-mode drivers use the **IoSetDeviceInterfacePropertyData** routine to modify device interface properties that are defined as part of the [unified device property model](/windows-hardware/drivers/install/unified-device-property-model--windows-vista-and-later-). For more information about device interface properties, see [Device Properties](/windows-hardware/drivers/image/device-properties).

Drivers can use the [IoGetDeviceInterfacePropertyData](./nf-wdm-iogetdeviceinterfacepropertydata.md) routine to obtain the current value for a device interface property.

Callers of **IoSetDeviceInterfacePropertyData** must be running at IRQL <= APC_LEVEL in the context of a system thread.

## -see-also

[DEVPROPKEY](/previous-versions/windows/hardware/drivers/dn315031(v=vs.85))

[DEVPROPTYPE](/previous-versions/ff543546(v=vs.85))

[IoGetDeviceInterfacePropertyData](./nf-wdm-iogetdeviceinterfacepropertydata.md)