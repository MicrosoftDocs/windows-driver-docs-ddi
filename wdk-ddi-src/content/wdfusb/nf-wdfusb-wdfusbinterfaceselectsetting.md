---
UID: NF:wdfusb.WdfUsbInterfaceSelectSetting
title: WdfUsbInterfaceSelectSetting function (wdfusb.h)
description: The WdfUsbInterfaceSelectSetting method selects a specified alternate setting for a specified USB interface.
old-location: wdf\wdfusbinterfaceselectsetting.htm
tech.root: wdf
ms.assetid: 398b7649-152e-4fed-b633-16627dadf0f8
ms.date: 02/26/2018
keywords: ["WdfUsbInterfaceSelectSetting function"]
ms.keywords: DFUsbRef_256e9b5d-8e9b-4935-9dc9-38a6071258a6.xml, WdfUsbInterfaceSelectSetting, WdfUsbInterfaceSelectSetting method, kmdf.wdfusbinterfaceselectsetting, wdf.wdfusbinterfaceselectsetting, wdfusb/WdfUsbInterfaceSelectSetting
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfUsbInterfaceSelectSetting
 - wdfusb/WdfUsbInterfaceSelectSetting
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfUsbInterfaceSelectSetting
---

# WdfUsbInterfaceSelectSetting function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceSelectSetting</b> method selects a specified alternate setting for a specified USB interface.

## -parameters

### -param UsbInterface 

[in]
A handle to a USB interface object that was obtained by calling <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>.

### -param PipesAttributes 

[in, optional]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for pipe objects that the framework creates for the interface. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param Params 

[in]
A pointer to a caller-supplied <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure that contains interface selection parameters.

## -returns

<b>WdfUsbInterfaceSelectSetting</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to create a new pipe object.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfUsbInterfaceSelectSetting</b> method might return, see <a href="/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method also might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

After your driver calls <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a> to select a configuration, the driver can call <b>WdfUsbInterfaceSelectSetting</b> to select an alternate setting for one of the device's interfaces.

Your driver can select an interface's alternate setting by specifying a USB interface descriptor or a <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>, or by just providing an alternate setting for the interface. In all cases, the driver must provide a handle to an interface object. 

If your driver just provides an alternate setting, the framework uses the interface object to determine the interface to which the setting belongs. 

If your driver specifies an interface descriptor or a URB, the framework uses the interface that is specified in the descriptor or URB.

The framework creates a framework USB pipe object for each pipe that is associated with the interface, after deleting any pipe objects that the framework might have previously created for the interface. To obtain information about an interface's pipe objects, your driver can call <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetnumconfiguredpipes">WdfUsbInterfaceGetNumConfiguredPipes</a> and <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>.

For more information about the <b>WdfUsbInterfaceSelectSetting</b> method and USB I/O targets, see <a href="/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example initializes a <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure with attributes for the pipe objects that the framework will create. Then, the example initializes a <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure to specify alternate setting 1. Finally, the example calls <b>WdfUsbInterfaceSelectSetting</b> to select the alternate setting and create pipe objects for the interface's pipes.

```cpp
WDF_OBJECT_ATTRIBUTES  pipesAttributes;
WDF_USB_INTERFACE_SELECT_SETTING_PARAMS  selectSettingParams;
NTSTATUS  Status;

WDF_OBJECT_ATTRIBUTES_INIT(&pipesAttributes);
WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE(
                                       &pipesAttributes,
                                       MY_PIPE_CONTEXT
                                       );

WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING(
                                      &selectSettingParams,
                                      1
                                      );

Status = WdfUsbInterfaceSelectSetting(
                                      UsbInterface,
                                      &pipesAttributes,
                                      &selectSettingParams
                                      );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="/windows-hardware/drivers/wdf/wdf-object-attributes-set-context-type">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_setting">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetnumconfiguredpipes">WdfUsbInterfaceGetNumConfiguredPipes</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a>