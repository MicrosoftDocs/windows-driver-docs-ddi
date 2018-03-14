---
UID: NE:wdfusb._WdfUsbTargetDeviceSelectSettingType
title: "_WdfUsbTargetDeviceSelectSettingType"
author: windows-driver-content
description: The WdfUsbTargetDeviceSelectSettingType enumeration defines techniques for specifying an alternate setting for a USB interface.
old-location: wdf\wdfusbtargetdeviceselectsettingtype.htm
old-project: wdf
ms.assetid: 3bbe3da6-f069-4965-ae60-2d755d7557c1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_2c08813e-959f-48db-92d5-3aece2d8e856.xml, WdfUsbInterfaceSelectSettingTypeDescriptor, WdfUsbInterfaceSelectSettingTypeSetting, WdfUsbInterfaceSelectSettingTypeUrb, WdfUsbTargetDeviceSelectSettingType, WdfUsbTargetDeviceSelectSettingType enumeration, _WdfUsbTargetDeviceSelectSettingType, kmdf.wdfusbtargetdeviceselectsettingtype, wdf.wdfusbtargetdeviceselectsettingtype, wdfusb/WdfUsbInterfaceSelectSettingTypeDescriptor, wdfusb/WdfUsbInterfaceSelectSettingTypeSetting, wdfusb/WdfUsbInterfaceSelectSettingTypeUrb, wdfusb/WdfUsbTargetDeviceSelectSettingType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: "<=DISPATCH_LEVEL  (See Remarks section.)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WdfUsbTargetDeviceSelectSettingType
product: Windows
targetos: Windows
req.typenames: WdfUsbTargetDeviceSelectSettingType
req.product: Windows 10 or later.
---

# _WdfUsbTargetDeviceSelectSettingType enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceSelectSettingType</b> enumeration defines techniques for specifying an alternate setting for a USB interface.


## -syntax


````
typedef enum _WdfUsbTargetDeviceSelectSettingType { 
  WdfUsbInterfaceSelectSettingTypeDescriptor  = 0x10,
  WdfUsbInterfaceSelectSettingTypeSetting     = 0x11,
  WdfUsbInterfaceSelectSettingTypeUrb         = 0x12
} WdfUsbTargetDeviceSelectSettingType;
````


## -enum-fields




### -field WdfUsbInterfaceSelectSettingTypeDescriptor

Specify an interface's alternate setting by providing a <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure.


### -field WdfUsbInterfaceSelectSettingTypeSetting

Specify an interface's alternate setting by providing a setting index value.


### -field WdfUsbInterfaceSelectSettingTypeUrb

Specify an interface's alternate setting by providing a <a href="..\usb\ns-usb-_urb.md">URB</a>.


## -remarks



The <b>WdfUsbTargetDeviceSelectSettingType</b> enumeration is used in the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure.




## -see-also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>



<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>



<a href="..\usb\ns-usb-_urb.md">URB</a>



 

 


