---
UID: NF:wdfusb.WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
title: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function
author: windows-driver-content
description: The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function initializes a WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure so that a driver can select a USB interface by specifying a URB.
old-location: wdf\wdf_usb_interface_select_setting_params_init_urb.htm
old-project: wdf
ms.assetid: 0c11941e-d0fc-4b0f-bf18-9920d371dd09
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdf_usb_interface_select_setting_params_init_urb, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function, wdf.wdf_usb_interface_select_setting_params_init_urb, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB, wdfusb/WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB, DFUsbRef_90777ed2-7cfd-422f-ba5b-423fd051e142.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfusb.h
apiname:
-	WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b> function initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure so that a driver can select a USB interface by specifying a URB.


## -syntax


````
VOID WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB(
  _Out_ PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS Params,
  _In_  PURB                                     Urb
);
````


## -parameters




### -param Params [out]

A pointer to a driver-allocated <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure.


### -param Urb [in]

A pointer to a <a href="..\usb\ns-usb-_urb.md">URB</a> structure.


## -returns



None




## -remarks



The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b> function zeros the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure and sets its <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbInterfaceSelectSettingTypeUrb</b> and sets the <b>Types.Urb.Urb</b> member to the value that is specified by <i>Urb</i> pointer.

To initialize a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure, your driver must call one of the following functions:

<ul>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_interface_select_setting_params_init_descriptor.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>


</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_interface_select_setting_params_init_setting.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>


</li>
<li>
<b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b>

</li>
</ul>

#### Examples

The following code example initializes a URB structure and then uses the structure as input to <a href="..\wdfusb\nf-wdfusb-wdfusbinterfaceselectsetting.md">WdfUsbInterfaceSelectSetting</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS  selectSettingParams;
URB  urb;
NTSTATUS  Status;

//
// Initialize the URB structure here.
//
...

//
// Initialize the WDF_USB_INTERFACE_SELECT_SETTING_PARAMS 
// structure and call WdfUsbInterfaceSelectSetting.
//
WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB(
                                      &amp;selectSettingParams,
                                      &amp;urb
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

<a href="..\wdfusb\nf-wdfusb-wdf_usb_interface_select_setting_params_init_descriptor.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>



<a href="..\wdfusb\nf-wdfusb-wdf_usb_interface_select_setting_params_init_setting.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>



<a href="..\usb\ns-usb-_urb.md">URB</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_select_setting_params.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

