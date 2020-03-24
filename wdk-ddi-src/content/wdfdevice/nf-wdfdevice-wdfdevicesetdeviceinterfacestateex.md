---
UID: NF:wdfdevice.WdfDeviceSetDeviceInterfaceStateEx
title: WdfDeviceSetDeviceInterfaceStateEx
ms.date: 03/24/2020
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdfdevice.h
req.idl: 
req.include-header: Wdf.h
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 1.31
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 1.31
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
 - WdfDeviceSetDeviceInterfaceStateEx
f1_keywords:
 - wdfdevice/WdfDeviceSetDeviceInterfaceStateEx
dev_langs:
 - c++
---

## -description

The <b>WdfDeviceSetDeviceInterfaceStateEx</b> method enables or disables a device interface for a specified device.


## -parameters

### -param Device

A handle to a framework device object.

### -param InterfaceClassGUID

A pointer to a GUID that identifies the device interface class.

### -param ReferenceString

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that describes a reference string for the device interface. This parameter is optional and can be <b>NULL</b>. 

### -param IsInterfaceEnabled

A Boolean value that, if <b>TRUE</b>, enables the specified device interface instance or, if <b>FALSE</b>, disables it.

## -remarks

The driver can call this function from [*EVT_WDF_DRIVER_DEVICE_ADD*](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add), or after the device has started. 
 
When calling from [*EVT_WDF_DRIVER_DEVICE_ADD*](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add), the driver should set **IsInterfaceEnabled** to FALSE. 
 
When calling after the device has started, the behavior is the same as [**WdfDeviceSetDeviceInterfaceState**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetdeviceinterfacestate). 

## -see-also

[**WdfDeviceSetDeviceInterfaceState**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetdeviceinterfacestate)

[Enabling and Disabling a Device Interface](/windows-hardware/drivers/wdf/using-device-interfaces#enabling-and-disabling-a-device-interface)