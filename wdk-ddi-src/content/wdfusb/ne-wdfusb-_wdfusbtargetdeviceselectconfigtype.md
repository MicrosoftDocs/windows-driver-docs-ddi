---
UID: NE:wdfusb._WdfUsbTargetDeviceSelectConfigType
title: _WdfUsbTargetDeviceSelectConfigType (wdfusb.h)
description: The WdfUsbTargetDeviceSelectConfigType enumeration defines types of configuration operations for USB devices.
old-location: wdf\wdfusbtargetdeviceselectconfigtype.htm
tech.root: wdf
ms.assetid: d3637f5e-d4c1-430c-8511-8aac18fceee2
ms.date: 02/26/2018
keywords: ["WdfUsbTargetDeviceSelectConfigType enumeration"]
ms.keywords: DFUsbRef_e4ab4d2c-dbca-4d6e-a690-4b362331e53e.xml, WdfUsbTargetDeviceSelectConfigType, WdfUsbTargetDeviceSelectConfigType enumeration, WdfUsbTargetDeviceSelectConfigTypeDeconfig, WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor, WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs, WdfUsbTargetDeviceSelectConfigTypeInvalid, WdfUsbTargetDeviceSelectConfigTypeMultiInterface, WdfUsbTargetDeviceSelectConfigTypeSingleInterface, WdfUsbTargetDeviceSelectConfigTypeUrb, _WdfUsbTargetDeviceSelectConfigType, kmdf.wdfusbtargetdeviceselectconfigtype, wdf.wdfusbtargetdeviceselectconfigtype, wdfusb/WdfUsbTargetDeviceSelectConfigType, wdfusb/WdfUsbTargetDeviceSelectConfigTypeDeconfig, wdfusb/WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor, wdfusb/WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs, wdfusb/WdfUsbTargetDeviceSelectConfigTypeInvalid, wdfusb/WdfUsbTargetDeviceSelectConfigTypeMultiInterface, wdfusb/WdfUsbTargetDeviceSelectConfigTypeSingleInterface, wdfusb/WdfUsbTargetDeviceSelectConfigTypeUrb
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
req.typenames: WdfUsbTargetDeviceSelectConfigType
f1_keywords:
 - _WdfUsbTargetDeviceSelectConfigType
 - wdfusb/_WdfUsbTargetDeviceSelectConfigType
 - WdfUsbTargetDeviceSelectConfigType
 - wdfusb/WdfUsbTargetDeviceSelectConfigType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfusb.h
api_name:
 - WdfUsbTargetDeviceSelectConfigType
---

# _WdfUsbTargetDeviceSelectConfigType enumeration


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceSelectConfigType</b> enumeration defines types of configuration operations for USB devices.

## -enum-fields

### -field WdfUsbTargetDeviceSelectConfigTypeInvalid

For internal use only.

### -field WdfUsbTargetDeviceSelectConfigTypeDeconfig

Deconfigure the device. This value applies to KMDF only.

### -field WdfUsbTargetDeviceSelectConfigTypeSingleInterface

Configure the device to use a single, specified interface. This value applies to KMDF and UMDF.

### -field WdfUsbTargetDeviceSelectConfigTypeMultiInterface

Configure the device to use multiple interfaces. This value applies to KMDF and UMDF.

### -field WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs

Configure the device to use multiple interfaces, possibly with alternate settings. Alternate settings are described in the USB specification.  This value applies to KMDF and UMDF.

### -field WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor

Configure the device by using configuration parameters that are contained in USB descriptors. This value applies to KMDF only.

### -field WdfUsbTargetDeviceSelectConfigTypeUrb

Configure the device by using configuration parameters that are contained in a driver-supplied URB structure. This value applies to KMDF only.

## -remarks

The <b>WdfUsbTargetDeviceSelectConfigType</b> enumeration is used to specify the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure. That structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a> method.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a>

