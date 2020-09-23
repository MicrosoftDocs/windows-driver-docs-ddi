---
UID: NF:wdfusb.WDF_USB_PIPE_INFORMATION_INIT
title: WDF_USB_PIPE_INFORMATION_INIT function (wdfusb.h)
description: The WDF_USB_PIPE_INFORMATION_INIT function initializes a WDF_USB_PIPE_INFORMATION structure.
old-location: wdf\wdf_usb_pipe_information_init.htm
tech.root: wdf
ms.assetid: 13139135-22b4-4ca1-b95e-c4c704501368
ms.date: 02/26/2018
keywords: ["WDF_USB_PIPE_INFORMATION_INIT function"]
ms.keywords: DFUsbRef_ed525fc0-384b-4e9c-877a-075386f5d667.xml, WDF_USB_PIPE_INFORMATION_INIT, WDF_USB_PIPE_INFORMATION_INIT function, kmdf.wdf_usb_pipe_information_init, wdf.wdf_usb_pipe_information_init, wdfusb/WDF_USB_PIPE_INFORMATION_INIT
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
 - WDF_USB_PIPE_INFORMATION_INIT
 - wdfusb/WDF_USB_PIPE_INFORMATION_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfusb.h
api_name:
 - WDF_USB_PIPE_INFORMATION_INIT
---

# WDF_USB_PIPE_INFORMATION_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_PIPE_INFORMATION_INIT</b> function initializes a <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a> structure.

## -parameters

### -param Info 

[out]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a> structure.

## -remarks

The <b>WDF_USB_PIPE_INFORMATION_INIT</b> function zeros the WDF_USB_PIPE_INFORMATION structure and sets the structure's <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_USB_PIPE_INFORMATION_INIT</b>, see <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetendpointinformation">WdfUsbInterfaceGetEndpointInformation</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a>