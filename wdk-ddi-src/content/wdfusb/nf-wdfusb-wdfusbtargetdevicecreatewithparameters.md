---
UID: NF:wdfusb.WdfUsbTargetDeviceCreateWithParameters
title: WdfUsbTargetDeviceCreateWithParameters function (wdfusb.h)
description: The WdfUsbTargetDeviceCreateWithParameters method creates a framework USB device object for a specified framework device object and opens the USB device for I/O operations.
old-location: wdf\wdfusbtargetdevicecreatewithparameters.htm
tech.root: wdf
ms.assetid: E93A944E-81D5-4059-ADA6-2760A091C30B
ms.date: 06/24/2019
ms.keywords: WdfUsbTargetDeviceCreateWithParameters, WdfUsbTargetDeviceCreateWithParameters method, kmdf.wdfusbtargetdevicecreatewithconfig, kmdf.wdfusbtargetdevicecreatewithparameters, wdf.wdfusbtargetdevicecreatewithparameters, wdfusb/WdfUsbTargetDeviceCreateWithParameters
ms.topic: function
f1_keywords:
 - "wdfusb/WdfUsbTargetDeviceCreateWithParameters"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, RequestForUrbXrb, UsbDeviceCreate, UsbDeviceCreateFail, UsbDeviceCreateTarget
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
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
- WdfUsbTargetDeviceCreateWithParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceCreateWithParameters function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>


   
  The <b>WdfUsbTargetDeviceCreateWithParameters</b>  method creates a framework USB device object for a specified framework device object and opens the USB device for I/O operations.
The method also specifies configuration information for the framework USB device object.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Config [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a> structure that contains configuration information for the framework USB device object.


### -param Attributes [in, optional]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new framework USB device object. (The structure's <b>ParentObject</b> member must be NULL.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param UsbDevice [out]

A pointer to a location that receives a handle to the new framework USB device object.


## -returns



<b>WdfUsbTargetDeviceCreateWithParameters</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>Config</i> parameter is not the correct size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to create a new framework USB device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.  See the Remarks section for more information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
An attempt to get USB configuration information failed.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfUsbTargetDeviceCreateWithParameters</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Windows 8 includes a new USB driver stack to support USB 3.0 devices.

Before a framework-based client driver can use the new capabilities of the USB driver stack for Windows 8, the driver must register itself with the underlying USB driver stack that is loaded by Windows for the device. To register the client driver, call <b>WdfUsbTargetDeviceCreateWithParameters</b> and specify a contract version in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a> structure.

 If the client driver is intended to build, run, and use the improvements and the new capabilities on Windows 8, the client contract version is USBD_CLIENT_CONTRACT_VERSION_602.

Typically, drivers call <b>WdfUsbTargetDeviceCreateWithParameters</b> from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function. Drivers can also call <b>WdfUsbTargetDeviceCreateWithParameters</b> from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

For information about how WDM USB client drivers interact with the USB 3.0 driver stack, see  <a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/usb-client-driver-contract-in-windows-8">Best Practices: Using URBs</a>.

If the driver calls <b>WdfUsbTargetDeviceCreateWithParameters</b> to create a framework USB device object, the driver must create URBs only by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreateurb">WdfUsbTargetDeviceCreateUrb</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreateisochurb">WdfUsbTargetDeviceCreateIsochUrb</a>.

If you call this method from a UMDF driver, you must specify the <b>UmdfDispatcher</b> directive in the driver's INF file.  Otherwise, this method may return <b>STATUS_INVALID_PARAMETER</b>.   For more information about this directive, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives in INF Files</a>.


#### Examples

The following code example is part of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function that calls <b>WdfUsbTargetDeviceCreateWithParameters</b>. The example stores the handle to the framework USB device object in driver-defined context space. 

```cpp
NTSTATUS
MyEvtDevicePrepareHardware(
    IN WDFDEVICE  Device,
    IN WDFCMRESLIST  ResourceList,
    IN WDFCMRESLIST  ResourceListTranslated
    )
{
    NTSTATUS  status;
    PMY_DEVICE_CONTEXT  pMyDeviceContext;
    WDF_USB_DEVICE_CREATE_CONFIG  Config;

    pMyDeviceContext = GetDeviceContext(Device);

    // If object handle is not NULL, MyEvtDevicePrepareHardware
    // was called previously and the handle is still valid.
    if (pMyDeviceContext->UsbDevice != NULL) {
        return STATUS_SUCCESS;
    }

    WDF_USB_DEVICE_CREATE_CONFIG_INIT(
                                      &Config,
                                      USBD_CLIENT_CONTRACT_VERSION_602
                                      );

    status = WdfUsbTargetDeviceCreateWithParameters(
                                      Device,
                                      &Config,
                                      WDF_NO_OBJECT_ATTRIBUTES,
                                      &pMyDeviceContext->UsbDevice
                                      );
    if (!NT_SUCCESS(status)) {
        return status;
    }
...
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_createhandle">USBD_CreateHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_device_create_config">WDF_USB_DEVICE_CREATE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_create_config_init">WDF_USB_DEVICE_CREATE_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreate">WdfUsbTargetDeviceCreate</a>
 

 

