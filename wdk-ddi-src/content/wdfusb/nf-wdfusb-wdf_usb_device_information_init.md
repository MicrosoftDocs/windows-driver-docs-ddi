---
UID: NF:wdfusb.WDF_USB_DEVICE_INFORMATION_INIT
title: WDF_USB_DEVICE_INFORMATION_INIT function (wdfusb.h)
description: The WDF_USB_DEVICE_INFORMATION_INIT function initializes a driver's WDF_USB_DEVICE_INFORMATION structure.
old-location: wdf\wdf_usb_device_information_init.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_USB_DEVICE_INFORMATION_INIT function"]
ms.keywords: DFUsbRef_ffde7966-f00b-4614-9845-aaebe2e0488b.xml, WDF_USB_DEVICE_INFORMATION_INIT, WDF_USB_DEVICE_INFORMATION_INIT function, kmdf.wdf_usb_device_information_init, wdf.wdf_usb_device_information_init, wdfusb/WDF_USB_DEVICE_INFORMATION_INIT
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
 - WDF_USB_DEVICE_INFORMATION_INIT
 - wdfusb/WDF_USB_DEVICE_INFORMATION_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfusb.h
api_name:
 - WDF_USB_DEVICE_INFORMATION_INIT
---

# WDF_USB_DEVICE_INFORMATION_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_DEVICE_INFORMATION_INIT</b> function initializes a driver's <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_information">WDF_USB_DEVICE_INFORMATION</a> structure.

## -parameters

### -param Udi 

[out]
A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_information">WDF_USB_DEVICE_INFORMATION</a> structure.

## -remarks

The <b>WDF_USB_DEVICE_INFORMATION_INIT</b> function zeros the <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_information">WDF_USB_DEVICE_INFORMATION</a> structure and sets its <b>Size</b> member to the size of the structure.


#### Examples

For a code example that uses<b>WDF_USB_DEVICE_INFORMATION_INIT</b>, see <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceretrieveinformation">WdfUsbTargetDeviceRetrieveInformation</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_information">WDF_USB_DEVICE_INFORMATION</a>
