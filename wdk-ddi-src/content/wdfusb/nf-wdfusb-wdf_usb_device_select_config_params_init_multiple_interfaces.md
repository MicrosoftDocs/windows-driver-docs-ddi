---
UID: NF:wdfusb.WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES
title: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function
author: windows-driver-content
description: The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can configure a device to use multiple interfaces.
old-location: wdf\wdf_usb_device_select_config_params_init_multiple_interfaces.htm
old-project: wdf
ms.assetid: e8f33c5d-50a4-43ad-a69e-d667500044a7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_185af305-36be-46f3-85d7-dfb3b3d4d6b8.xml, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function, kmdf.wdf_usb_device_select_config_params_init_multiple_interfaces, wdf.wdf_usb_device_select_config_params_init_multiple_interfaces, wdfusb/WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES
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
-	WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure so that a driver can configure a device to use multiple interfaces.


## -parameters




### -param Params [in, out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure.


### -param NumberInterfaces [in, optional]

The number of elements in the <i>SettingPairs</i> array. If <i>SettingPairs</i> is not <b>NULL</b>, this parameter must be greater than zero. 


### -param SettingPairs [in, optional]

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff553023">WDF_USB_INTERFACE_SETTING_PAIR</a> structures. This parameter is optional and can be <b>NULL</b>.


## -returns



None




## -remarks



Your driver can use the <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> function to select a configuration if the device interfaces are specified by handles to USB interface objects. 

Your driver can use this function if your device has one or more USB interfaces.

The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> function zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure and sets the <b>Size</b> member to the size of the structure. 

If either <i>numInterfaces</i> or <i>SettingPairs</i> is <b>NULL</b>, <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> sets the <b>Type</b> member to <b>WdfUsbTargetDeviceSelectConfigTypeMultiInterface</b>. In this case, the framework determines the number of interfaces you have and enables alternate setting zero on each. Use this setting if you would like to default to alternate setting zero on all interfaces.


If the <i>numInterfaces</i> parameter and the <i>SettingPairs</i> parameter are both not <b>NULL</b>, this function sets the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure to <b>WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs</b>. In this case, you can specify an alternate setting on any of the interfaces.

To initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure, the driver must call one of the following functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552982">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552995">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>


</li>
<li>
<b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b>

</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552986">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552997">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>


</li>
</ul>

#### Examples

The following code example calls either <a href="https://msdn.microsoft.com/library/windows/hardware/ff552995">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a> or <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b>, based on the number of interfaces that the device configuration supports. Then, the example calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550101">WdfUsbTargetDeviceSelectConfig</a> to select a configuration.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552982">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552986">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552992">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552995">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552997">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553023">WDF_USB_INTERFACE_SETTING_PAIR</a>
 

 

