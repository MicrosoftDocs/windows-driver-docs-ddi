---
UID: NE:wdfusb._WdfUsbTargetDeviceSelectSettingType
title: _WdfUsbTargetDeviceSelectSettingType (wdfusb.h)
description: The WdfUsbTargetDeviceSelectSettingType enumeration defines techniques for specifying an alternate setting for a USB interface.
old-location: wdf\wdfusbtargetdeviceselectsettingtype.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfUsbTargetDeviceSelectSettingType enumeration"]
ms.keywords: DFUsbRef_2c08813e-959f-48db-92d5-3aece2d8e856.xml, WdfUsbInterfaceSelectSettingTypeDescriptor, WdfUsbInterfaceSelectSettingTypeSetting, WdfUsbInterfaceSelectSettingTypeUrb, WdfUsbTargetDeviceSelectSettingType, WdfUsbTargetDeviceSelectSettingType enumeration, _WdfUsbTargetDeviceSelectSettingType, kmdf.wdfusbtargetdeviceselectsettingtype, wdf.wdfusbtargetdeviceselectsettingtype, wdfusb/WdfUsbInterfaceSelectSettingTypeDescriptor, wdfusb/WdfUsbInterfaceSelectSettingTypeSetting, wdfusb/WdfUsbInterfaceSelectSettingTypeUrb, wdfusb/WdfUsbTargetDeviceSelectSettingType
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WdfUsbTargetDeviceSelectSettingType
f1_keywords:
 - _WdfUsbTargetDeviceSelectSettingType
 - wdfusb/_WdfUsbTargetDeviceSelectSettingType
 - WdfUsbTargetDeviceSelectSettingType
 - wdfusb/WdfUsbTargetDeviceSelectSettingType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfusb.h
api_name:
 - _WdfUsbTargetDeviceSelectSettingType
 - WdfUsbTargetDeviceSelectSettingType
---

# _WdfUsbTargetDeviceSelectSettingType enumeration


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceSelectSettingType</b> enumeration defines techniques for specifying an alternate setting for a USB interface.

## -enum-fields

### -field WdfUsbInterfaceSelectSettingTypeDescriptor:0x10

Specify an interface's alternate setting by providing a <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> structure.

### -field WdfUsbInterfaceSelectSettingTypeSetting:0x11

Specify an interface's alternate setting by providing a setting index value.

### -field WdfUsbInterfaceSelectSettingTypeUrb:0x12

Specify an interface's alternate setting by providing a <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>.

## -remarks

The <b>WdfUsbTargetDeviceSelectSettingType</b> enumeration is used in the <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>

