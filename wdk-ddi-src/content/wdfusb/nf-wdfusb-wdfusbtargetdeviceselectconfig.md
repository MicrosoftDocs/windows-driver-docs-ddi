---
UID: NF:wdfusb.WdfUsbTargetDeviceSelectConfig
title: WdfUsbTargetDeviceSelectConfig function
author: windows-driver-content
description: The WdfUsbTargetDeviceSelectConfig method selects a USB configuration for a device, or it deconfigures the device.
old-location: wdf\wdfusbtargetdeviceselectconfig.htm
old-project: wdf
ms.assetid: 6f5ab951-0652-477c-8a0a-71d1b94d08c6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , C, D, DFUsbRef_9f390705-2077-43ca-a1b9-0be087c86619.xml, S, T, U, W, WdfUsbTargetDeviceSelectConfig, WdfUsbTargetDeviceSelectConfig method, a, b, c, d, e, f, g, i, kmdf.wdfusbtargetdeviceselectconfig, l, n, o, r, s, t, v, wdf.wdfusbtargetdeviceselectconfig, wdfusb/WdfUsbTargetDeviceSelectConfig"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfUsbTargetDeviceSelectConfig
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceSelectConfig function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceSelectConfig</b> method selects a USB configuration for a device, or it deconfigures the device.


## -syntax


````
NTSTATUS WdfUsbTargetDeviceSelectConfig(
  _In_     WDFUSBDEVICE                         UsbDevice,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES               PipeAttributes,
  _Inout_  PWDF_USB_DEVICE_SELECT_CONFIG_PARAMS Params
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param PipeAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for new framework USB pipe objects that the framework creates for the device's interfaces. For KMDF drivers, this parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. UMDF drivers must set this parameter to NULL.


### -param Params [in, out]

A pointer to a caller-allocated <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure that the caller and the framework use to specify configuration parameters. 


## -returns



<b>WdfUsbTargetDeviceSelectConfig</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:

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
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <b>Size</b> member of the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure that <i>Params</i> points to was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A memory buffer could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The framework returns this value if a UMDF driver calls <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a> with <i>Params</i>-&gt;<b>Type</b> set to any of the following:

<ul>
<li><b>WdfUsbTargetDeviceSelectConfigTypeDeconfig</b></li>
<li><b>WdfUsbTargetDeviceSelectConfigTypeInterfacesDescriptor</b></li>
<li><b>WdfUsbTargetDeviceSelectConfigTypeUrb</b></li>
</ul>
For more info, see <a href="..\wdfusb\ne-wdfusb-_wdfusbtargetdeviceselectconfigtype.md">WdfUsbTargetDeviceSelectConfigType</a>.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver can select a device configuration by using a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure to specify USB descriptors, a URB, or handles to framework USB interface objects.

The framework creates a framework USB pipe object for each pipe that is associated with each interface in the configuration, after deleting any pipe objects that the framework might have previously created for the configuration. The framework uses alternate setting zero for each interface, unless the driver specifies a different alternate setting.

To obtain information about an interface's pipe objects, the driver can call <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetnumconfiguredpipes.md">WdfUsbInterfaceGetNumConfiguredPipes</a> and <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>.

For more information about the <b>WdfUsbTargetDeviceSelectConfig</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

<div class="alert"><b>Caution</b>  <p class="note">You can use <b>WdfUsbTargetDeviceSelectConfig</b> to select only the first USB configuration listed in the descriptor list, but you can select multiple interfaces within this single configuration.

</div>
<div> </div>

#### Examples

The following code example selects a configuration with a single, specified  interface. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS  configParams;
NTSTATUS  status;

WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE(&amp;configParams);

status = WdfUsbTargetDeviceSelectConfig(
                                        UsbDevice,
                                        WDF_NO_OBJECT_ATTRIBUTES,
                                        &amp;configParams
                                        );</pre>
</td>
</tr>
</table></span></div>
The following code example selects a configuration with multiple interfaces, using alternate setting zero on all interfaces. This example applies only to KMDF drivers.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS  configParams;
PWDF_USB_INTERFACE_SETTING_PAIR settingPairs;
UCHAR numInterfaces;
NTSTATUS  status;

numInterfaces = WdfUsbTargetDeviceGetNumInterfaces(UsbDevice);

settingPairs = ExAllocatePoolWithTag(
    PagedPool,
    sizeof(WDF_USB_INTERFACE_SETTING_PAIR) * numInterfaces,
    MY_DRIVER_TAG
);

if (settingPairs == NULL){
    return STATUS_INSUFFICIENT_RESOURCES;
}

for (interfaceIndex = 0; interfaceIndex &lt; numInterfaces; interfaceIndex++) {
        
    settingPairs[interfaceIndex].UsbInterface = 
                                    WdfUsbTargetDeviceGetInterface(
                                        UsbDevice,
                                        interfaceIndex);

    // Select alternate setting zero on all interfaces.
       
    settingPairs[interfaceIndex].SettingIndex = 0;
}

WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES(
    &amp;configParams,
    numInterfaces,
    settingPairs
);

status = WdfUsbTargetDeviceSelectConfig(
    UsbDevice,
    NULL,
    &amp;configParams
);

if (!NT_SUCCESS(status)) {
    ExFreePoolWithTag(
        settingPairs,
        MY_DRIVER_TAG
    );
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetnumconfiguredpipes.md">WdfUsbInterfaceGetNumConfiguredPipes</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_single_interface.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>



<a href="..\wdfusb\nf-wdfusb-wdf_usb_device_select_config_params_init_multiple_interfaces.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_select_config_params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceSelectConfig method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

