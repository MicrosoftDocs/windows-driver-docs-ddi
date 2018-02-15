---
UID: NF:wdfusb.WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES
title: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function
author: windows-driver-content
description: The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can configure a device to use multiple interfaces.
old-location: wdf\wdf_usb_device_select_config_params_init_multiple_interfaces.htm
old-project: wdf
ms.assetid: e8f33c5d-50a4-43ad-a69e-d667500044a7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdf_usb_device_select_config_params_init_multiple_interfaces, wdf.wdf_usb_device_select_config_params_init_multiple_interfaces, DFUsbRef_185af305-36be-46f3-85d7-dfb3b3d4d6b8.xml, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES, wdfusb/WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES
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
-	WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> function initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure so that a driver can configure a device to use multiple interfaces.


## -syntax


````
VOID WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES(
  _Inout_  PWDF_USB_DEVICE_SELECT_CONFIG_PARAMS Params,
  _In_opt_ UCHAR                                NumberInterfaces,
  _In_opt_ PWDF_USB_INTERFACE_SETTING_PAIR      SettingPairs
);
````


## -parameters




### -param Params [in, out]

A pointer to a driver-allocated <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure.


### -param NumberInterfaces [in, optional]

The number of elements in the <i>SettingPairs</i> array. If <i>SettingPairs</i> is not <b>NULL</b>, this parameter must be greater than zero. 


### -param SettingPairs [in, optional]

An array of <a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_setting_pair.md">WDF_USB_INTERFACE_SETTING_PAIR</a> structures. This parameter is optional and can be <b>NULL</b>.


## -returns



None




## -remarks



Your driver can use the <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> function to select a configuration if the device interfaces are specified by handles to USB interface objects. 

Your driver can use this function if your device has one or more USB interfaces.

The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> function zeros the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure and sets the <b>Size</b> member to the size of the structure. 

If either <i>numInterfaces</i> or <i>SettingPairs</i> is <b>NULL</b>, <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> sets the <b>Type</b> member to <b>WdfUsbTargetDeviceSelectConfigTypeMultiInterface</b>. In this case, the framework determines the number of interfaces you have and enables alternate setting zero on each. Use this setting if you would like to default to alternate setting zero on all interfaces.


If the <i>numInterfaces</i> parameter and the <i>SettingPairs</i> parameter are both not <b>NULL</b>, this function sets the <b>Type</b> member of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure to <b>WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs</b>. In this case, you can specify an alternate setting on any of the interfaces.

To initialize a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure, the driver must call one of the following functions:

<ul>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_deconfig.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>


</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_single_interface.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>


</li>
<li>
<b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b>

</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_interfaces_descriptors.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>


</li>
<li>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_urb.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>


</li>
</ul>

#### Examples

The following code example calls either <a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_single_interface.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a> or <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b>, based on the number of interfaces that the device configuration supports. Then, the example calls <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a> to select a configuration.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS params;
PWDF_USB_INTERFACE_SETTING_PAIR settingPairs;
UCHAR numInterfaces;

numInterfaces = WdfUsbTargetDeviceGetNumInterfaces(UsbDevice);

if (numInterfaces == 1){
    WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE(&amp;params);
}
else {
    settingPairs = ExAllocatePoolWithTag(
                        PagedPool,
                        sizeof(WDF_USB_INTERFACE_SETTING_PAIR) * numInterfaces,
                        MEM_TAG
                        );
    if (settingPairs == NULL){
        return STATUS_INSUFFICIENT_RESOURCES;
    }

 //
 // Call driver-defined routine to populate the
    // WDF_USB_INTERFACE_SETTING_PAIR structures 
 // that ExAllocatePoolWithTag allocated.
 //
    InitSettingPairs(
                     UsbDevice,
                     settingPairs,
                     numInterfaces
                     );

    WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES(
                    &amp;params,
                    numInterfaces,
                    settingPairs
                    );
}
status = WdfUsbTargetDeviceSelectConfig(
                                        UsbDevice,
                                        NULL,
                                        &amp;params
                                        );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_interfaces_descriptors.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_interface_setting_pair.md">WDF_USB_INTERFACE_SETTING_PAIR</a>



<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_single_interface.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>



<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_urb.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>



<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_deconfig.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>



<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_multiple_interfaces.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

