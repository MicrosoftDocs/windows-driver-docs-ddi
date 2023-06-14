---
UID: NF:wdfdevice.WdfDeviceSetDeviceInterfaceStateEx
title: WdfDeviceSetDeviceInterfaceStateEx
tech.root: wdf
ms.date: 06/14/2023
targetos: Windows
description: "Learn more about: WdfDeviceSetDeviceInterfaceStateEx"
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
req.target-min-winverclnt: Windows 10, version 2004
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
 - WdfDeviceSetDeviceInterfaceStateEx
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

A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that describes a reference string for the device interface. This parameter is optional and can be <b>NULL</b>.

### -param IsInterfaceEnabled

A Boolean value that, if <b>TRUE</b>, enables the specified device interface instance or, if <b>FALSE</b>, disables it.

## -remarks

The driver can call this function either before or after the device has started.

When called before the device starts (for example from [*EvtDriverDeviceAdd*](/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add), [*EvtChildListCreateDevice*](/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device), or [*EvtDevicePrepareHardware*](/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware)), the driver should set **IsInterfaceEnabled** to FALSE to prevent the interface from being automatically enabled during PnP start. Setting the parameter to TRUE before the device starts is meaningless and should be avoided.

When calling after the device has started, the behavior is the same as [**WdfDeviceSetDeviceInterfaceState**](./nf-wdfdevice-wdfdevicesetdeviceinterfacestate.md).

## -see-also

[**WdfDeviceSetDeviceInterfaceState**](./nf-wdfdevice-wdfdevicesetdeviceinterfacestate.md)

[Enabling and Disabling a Device Interface](/windows-hardware/drivers/wdf/using-device-interfaces#enabling-and-disabling-a-device-interface)
