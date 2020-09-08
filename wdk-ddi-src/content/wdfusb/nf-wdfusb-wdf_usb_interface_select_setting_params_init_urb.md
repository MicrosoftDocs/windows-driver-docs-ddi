---
UID: NF:wdfusb.WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
title: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function (wdfusb.h)
description: The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function initializes a WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure so that a driver can select a USB interface by specifying a URB.
old-location: wdf\wdf_usb_interface_select_setting_params_init_urb.htm
tech.root: wdf
ms.assetid: 0c11941e-d0fc-4b0f-bf18-9920d371dd09
ms.date: 02/26/2018
keywords: ["WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function"]
ms.keywords: DFUsbRef_90777ed2-7cfd-422f-ba5b-423fd051e142.xml, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function, kmdf.wdf_usb_interface_select_setting_params_init_urb, wdf.wdf_usb_interface_select_setting_params_init_urb, wdfusb/WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
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
 - WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
 - wdfusb/WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfusb.h
api_name:
 - WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB
---

# WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure so that a driver can select a USB interface by specifying a URB.

## -parameters

### -param Params 

[out]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure.

### -param Urb 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure.

## -remarks

The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b> function zeros the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure and sets its <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbInterfaceSelectSettingTypeUrb</b> and sets the <b>Types.Urb.Urb</b> member to the value that is specified by <i>Urb</i> pointer.

To initialize a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure, your driver must call one of the following functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_descriptor">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_setting">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>


</li>
<li>
<b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</b>

</li>
</ul>

#### Examples

The following code example initializes a URB structure and then uses the structure as input to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfaceselectsetting">WdfUsbInterfaceSelectSetting</a>.

```cpp
WDF_USB_INTERFACE_SELECT_SETTING_PARAMS  selectSettingParams;
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
                                      &selectSettingParams,
                                      &urb
                                      );

Status = WdfUsbInterfaceSelectSetting(
                                      UsbInterface,
                                      WDF_NO_OBJECT_ATTRIBUTES,
                                      &selectSettingParams
                                      );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_descriptor">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_setting">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>

