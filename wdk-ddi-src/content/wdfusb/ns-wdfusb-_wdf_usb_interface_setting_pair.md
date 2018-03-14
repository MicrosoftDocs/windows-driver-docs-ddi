---
UID: NS:wdfusb._WDF_USB_INTERFACE_SETTING_PAIR
title: "_WDF_USB_INTERFACE_SETTING_PAIR"
author: windows-driver-content
description: The WDF_USB_INTERFACE_SETTING_PAIR structure specifies an alternate setting for a specified USB interface.
old-location: wdf\wdf_usb_interface_setting_pair.htm
old-project: wdf
ms.assetid: b6f169ae-6c4c-4c27-8532-75a76b66cc5a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_USB_INTERFACE_SETTING_PAIR, DFUsbRef_e8de7f02-5d9b-4cba-9e7c-dc4562256f9e.xml, PWDF_USB_INTERFACE_SETTING_PAIR, PWDF_USB_INTERFACE_SETTING_PAIR structure pointer, WDF_USB_INTERFACE_SETTING_PAIR, WDF_USB_INTERFACE_SETTING_PAIR structure, _WDF_USB_INTERFACE_SETTING_PAIR, kmdf.wdf_usb_interface_setting_pair, wdf.wdf_usb_interface_setting_pair, wdfusb/PWDF_USB_INTERFACE_SETTING_PAIR, wdfusb/WDF_USB_INTERFACE_SETTING_PAIR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_INTERFACE_SETTING_PAIR
product: Windows
targetos: Windows
req.typenames: WDF_USB_INTERFACE_SETTING_PAIR, *PWDF_USB_INTERFACE_SETTING_PAIR
req.product: Windows 10 or later.
---

# _WDF_USB_INTERFACE_SETTING_PAIR structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_INTERFACE_SETTING_PAIR</b> structure specifies an alternate setting for a specified USB interface.


## -syntax


````
typedef struct _WDF_USB_INTERFACE_SETTING_PAIR {
  WDFUSBINTERFACE UsbInterface;
  UCHAR           SettingIndex;
} WDF_USB_INTERFACE_SETTING_PAIR, *PWDF_USB_INTERFACE_SETTING_PAIR;
````


## -struct-fields




### -field UsbInterface

A handle to a framework USB interface object.


### -field SettingIndex

A device-specific index value that identifies an alternate setting for the interface. Alternate settings are described in the USB specification.


## -remarks



The <b>WDF_USB_INTERFACE_SETTING_PAIR</b> structure is used in the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure.




## -see-also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>



 

 


