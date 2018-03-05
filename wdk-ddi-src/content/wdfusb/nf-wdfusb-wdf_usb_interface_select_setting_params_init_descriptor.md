---
UID: NF:wdfusb.WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR
title: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR function
author: windows-driver-content
description: The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR function initializes a WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure so that a driver can select a USB interface by specifying an interface descriptor.
old-location: wdf\wdf_usb_interface_select_setting_params_init_descriptor.htm
old-project: wdf
ms.assetid: ae9266a2-1bfe-4b5f-b745-b7bfe4f0bfca
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_6c30fa1b-546f-46f2-8eb6-fd189894a746.xml, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR function, kmdf.wdf_usb_interface_select_setting_params_init_descriptor, wdf.wdf_usb_interface_select_setting_params_init_descriptor, wdfusb/WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR
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
req.lib: NtosKrnl.exe
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
-	WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</b> function initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure so that a driver can select a USB interface by specifying an interface descriptor.


## -syntax


````
VOID WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR(
  _Out_ PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS Params,
  _In_  PUSB_INTERFACE_DESCRIPTOR                Interface
);
````


## -parameters




### -param Params [out]

A pointer to a driver-allocated <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure.


### -param Interface [in]

A pointer to a <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure.


## -returns



None




## -remarks



The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</b> function zeros the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure and sets its <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbInterfaceSelectSettingTypeDescriptor</b> and sets the <b>Types.Descriptor.InterfaceDescriptor</b> member to the value of the <i>Interface</i> pointer.

To initialize a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure, your driver must call one of the following functions:

<ul>
<li>
<b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</b>

</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_interface_select_setting_params_init_setting.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>


</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_interface_select_setting_params_init_urb.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</a>


</li>
</ul>

#### Examples

The following code example initializes a <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure and then uses the structure as input to <a href="..\wdfusb\nf-wdfusb-wdfusbinterfaceselectsetting.md">WdfUsbInterfaceSelectSetting</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS  selectSettingParams;
USB_INTERFACE_DESCRIPTOR  interfaceDescriptor;
NTSTATUS  Status;

//
// Initialize the USB_INTERFACE_DESCRIPTOR structure here.
//
...

//
// Initialize the WDF_USB_INTERFACE_SELECT_SETTING_PARAMS 
// structure and call WdfUsbInterfaceSelectSetting.
//
WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR(
                                      &amp;selectSettingParams,
                                      &amp;interfaceDescriptor
                                      );

Status = WdfUsbInterfaceSelectSetting(
                                      UsbInterface,
                                      WDF_NO_OBJECT_ATTRIBUTES,
                                      &amp;selectSettingParams
                                      );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>



<a href="..\wdfusb\nf-wdfusb-wdf_usb_interface_select_setting_params_init_urb.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</a>



<a href="..\wdfusb\nf-wdfusb-wdf_usb_interface_select_setting_params_init_setting.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

