---
UID: NF:wdfusb.WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG
title: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG function (wdfusb.h)
description: The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can deconfigure a USB device.
old-location: wdf\wdf_usb_device_select_config_params_init_deconfig.htm
tech.root: wdf
ms.assetid: cc7ee273-e445-4cdb-b96d-b63db6e433de
ms.date: 02/26/2018
keywords: ["WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG function"]
ms.keywords: DFUsbRef_9dcc7843-1cc0-4af0-9763-31fbac46ce41.xml, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG, WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG function, kmdf.wdf_usb_device_select_config_params_init_deconfig, wdf.wdf_usb_device_select_config_params_init_deconfig, wdfusb/WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG
 - wdfusb/WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfusb.h
api_name:
 - WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG
---

# WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure so that a driver can deconfigure a USB device.

## -parameters

### -param Params 

[out]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure.

## -remarks

The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</b> function zeros the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure and sets the <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbTargetDeviceSelectConfigTypeDeconfig</b>.

To initialize a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure, the driver must call one of the following functions:

<ul>
<li>
<b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</b>

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_select_config_params_init_single_interface">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_select_config_params_init_multiple_interfaces">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_select_config_params_init_interfaces_descriptors">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_select_config_params_init_urb">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>


</li>
</ul>

#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure and then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a> to deconfigure a device.

```cpp
WDF_USB_DEVICE_SELECT_CONFIG_PARAMS configParams;
NTSTATUS status;

WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG(&configParams);
Status = WdfUsbTargetDeviceSelectConfig(
                                        UsbDevice,
                                        WDF_NO_OBJECT_ATTRIBUTES,
                                        &configParams
                                        );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_select_config_params_init_deconfig">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_select_config_params_init_interfaces_descriptors">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_select_config_params_init_multiple_interfaces">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_select_config_params_init_single_interface">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_select_config_params_init_urb">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>

