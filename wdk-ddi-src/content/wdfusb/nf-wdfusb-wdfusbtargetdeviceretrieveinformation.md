---
UID: NF:wdfusb.WdfUsbTargetDeviceRetrieveInformation
title: WdfUsbTargetDeviceRetrieveInformation function (wdfusb.h)
description: The WdfUsbTargetDeviceRetrieveInformation method retrieves information about the USB device that is associated with a specified framework USB device object.
old-location: wdf\wdfusbtargetdeviceretrieveinformation.htm
tech.root: wdf
ms.assetid: 68fc8d8b-3ba2-4f22-8a7e-29971a38544b
ms.date: 02/26/2018
ms.keywords: DFUsbRef_dd8528c2-9697-4cc3-88f2-ba198fbe7594.xml, WdfUsbTargetDeviceRetrieveInformation, WdfUsbTargetDeviceRetrieveInformation method, kmdf.wdfusbtargetdeviceretrieveinformation, wdf.wdfusbtargetdeviceretrieveinformation, wdfusb/WdfUsbTargetDeviceRetrieveInformation
ms.topic: function
f1_keywords:
 - "wdfusb/WdfUsbTargetDeviceRetrieveInformation"
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
req.irql: <=DISPATCH_LEVEL
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
- WdfUsbTargetDeviceRetrieveInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceRetrieveInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceRetrieveInformation</b> method retrieves information about the USB device that is associated with a specified framework USB device object.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Information [out]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_device_information">WDF_USB_DEVICE_INFORMATION</a> structure that receives USB device information.


## -returns



<b>WdfUsbTargetDeviceRetrieveInformation</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbTargetDeviceRetrieveInformation</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.

In framework versions 1.11 and later, the driver  can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicequeryusbcapability">WdfUsbTargetDeviceQueryUsbCapability</a> to retrieve a device's operating speed.


#### Examples

The following code example is part of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function that creates a USB device object, initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_device_information">WDF_USB_DEVICE_INFORMATION</a> structure, and calls <b>WdfUsbTargetDeviceRetrieveInformation</b>. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
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

    WDF_USB_DEVICE_INFORMATION_INIT(&deviceInfo);

    status = WdfUsbTargetDeviceRetrieveInformation(
                                      pDeviceContext->UsbDevice, 
                                      &deviceInfo
                                      );
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_device_information">WDF_USB_DEVICE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicequeryusbcapability">WdfUsbTargetDeviceQueryUsbCapability</a>
 

 

