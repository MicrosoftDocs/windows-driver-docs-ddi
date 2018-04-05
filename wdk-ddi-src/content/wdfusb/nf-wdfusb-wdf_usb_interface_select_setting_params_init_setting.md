---
UID: NF:wdfusb.WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING
title: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function
author: windows-driver-content
description: The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function initializes a WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure so that a driver can select a USB interface by specifying a handle to an interface object and an alternate setting for the interface.
old-location: wdf\wdf_usb_interface_select_setting_params_init_setting.htm
old-project: wdf
ms.assetid: 2b58eb8f-c468-4bc6-ad50-0bc9f2dee561
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_9f764089-ac6f-404a-8196-170547e40495.xml, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function, kmdf.wdf_usb_interface_select_setting_params_init_setting, wdf.wdf_usb_interface_select_setting_params_init_setting, wdfusb/WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
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
-	WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure so that a driver can select a USB interface by specifying a handle to an interface object and an alternate setting for the interface.


## -parameters




### -param Params [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure.


### -param SettingIndex [in]

An index value that identifies an alternate setting for the interface. (The interface is identified by an interface object handle that the driver passes to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550073">WdfUsbInterfaceSelectSetting</a>.) 


## -returns



None




## -remarks



The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</b> function zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure and sets its <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbInterfaceSelectSettingTypeSetting</b> and sets the <b>Types.Interface.SettingIndex</b> member to the value that is specified by <i>SettingIndex</i>.

To initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure, your driver must call one of the following functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553008">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>


</li>
<li>
<b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</b>

</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553016">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</a>


</li>
</ul>
For a code example that uses <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550073">WdfUsbInterfaceSelectSetting</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553008">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553016">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550073">WdfUsbInterfaceSelectSetting</a>
 

 

