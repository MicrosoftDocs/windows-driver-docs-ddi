---
UID: NF:wdfusb.WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE
title: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE function
author: windows-driver-content
description: The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can configure a device to use a single, specified interface.
old-location: wdf\wdf_usb_device_select_config_params_init_single_interface.htm
old-project: wdf
ms.assetid: c0dfcc32-7a32-4d76-b954-de2c9c188353
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_a1c68810-efa7-4438-ab8b-ea6ea881d941.xml, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE function, kmdf.wdf_usb_device_select_config_params_init_single_interface, wdf.wdf_usb_device_select_config_params_init_single_interface, wdfusb/WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE
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
-	WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE
product: Windows
targetos: Windows
req.typenames: 
---

# WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure so that a driver can configure a device to use a single, specified interface. 


## -parameters




### -param Params [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure.


## -returns



None




## -remarks



Your driver can use the <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</b> function to select a configuration if the device interface is specified by a handle to USB interface objects. 

Your driver can use this function only if your device has just one USB interface.

The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</b> function zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure and sets the <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbTargetDeviceSelectConfigTypeSingleInterface</b>.

To initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure, the driver must call one of the following functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552982">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>


</li>
<li>
<b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</b>

</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552992">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552986">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552997">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>


</li>
</ul>
For a code example that uses <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550101">WdfUsbTargetDeviceSelectConfig</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552982">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552986">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552992">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552995">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552997">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>
 

 

