---
UID: NF:wdfusb.WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB
title: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB function (wdfusb.h)
description: The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can specify a configuration by using a URB.
old-location: wdf\wdf_usb_device_select_config_params_init_urb.htm
tech.root: wdf
ms.assetid: 087888ce-e08a-4f9f-adac-419a638e65bd
ms.date: 02/26/2018
ms.keywords: DFUsbRef_bb81c111-ac7f-4f37-bda6-c09ebc32e5fd.xml, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB function, kmdf.wdf_usb_device_select_config_params_init_urb, wdf.wdf_usb_device_select_config_params_init_urb, wdfusb/WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfusb.h
api_name:
- WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure so that a driver can specify a configuration by using a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>. 


## -parameters




### -param Params [out]

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure.


### -param Urb [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure.


## -returns



None




## -remarks



The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</b> function zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure and sets the <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbTargetDeviceSelectConfigTypeUrb</b> and sets the <b>Types.Urb.Urb</b> member to the <i>Urb</i> pointer.

To initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure, the driver must call one of the following functions:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff552982">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552995">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552992">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552986">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>


<b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</b>




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552600">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>
 

 

