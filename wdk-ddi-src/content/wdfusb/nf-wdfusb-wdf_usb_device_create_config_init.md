---
UID: NF:wdfusb.WDF_USB_DEVICE_CREATE_CONFIG_INIT
title: WDF_USB_DEVICE_CREATE_CONFIG_INIT function (wdfusb.h)
description: The WDF_USB_DEVICE_CREATE_CONFIG_INIT function initializes a WDF_USB_DEVICE_CREATE_CONFIG structure.
old-location: wdf\wdf_usb_device_create_config_init.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_USB_DEVICE_CREATE_CONFIG_INIT function"]
ms.keywords: WDF_USB_DEVICE_CREATE_CONFIG_INIT, WDF_USB_DEVICE_CREATE_CONFIG_INIT function, kmdf.wdf_usb_device_create_config_init, kmdf.wdf_usbtarget_device_config_init, wdf.wdf_usb_device_create_config_init, wdfusb/WDF_USB_DEVICE_CREATE_CONFIG_INIT
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
 - WDF_USB_DEVICE_CREATE_CONFIG_INIT
 - wdfusb/WDF_USB_DEVICE_CREATE_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfusb.h
api_name:
 - WDF_USB_DEVICE_CREATE_CONFIG_INIT
---

# WDF_USB_DEVICE_CREATE_CONFIG_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b> function
  initializes a <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a> structure.

## -parameters

### -param Config [out]


A pointer to a <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a> structure.

### -param USBDClientContractVersion [in]


The contract version that the client driver supports. <b>USBDClientContractVersion</b> must be USBD_CLIENT_CONTRACT_VERSION_602.

## -remarks

The <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b> function zeros the specified <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a> structure and sets the <b>Size</b> member to the size of the structure. It also sets the structure's <b>USBDClientContractVersion</b> member to the specified value.

For a code example that uses <b>WDF_USB_DEVICE_CREATE_CONFIG_INIT</b>, see <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>
