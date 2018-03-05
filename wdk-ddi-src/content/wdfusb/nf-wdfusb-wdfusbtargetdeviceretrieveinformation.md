---
UID: NF:wdfusb.WdfUsbTargetDeviceRetrieveInformation
title: WdfUsbTargetDeviceRetrieveInformation function
author: windows-driver-content
description: The WdfUsbTargetDeviceRetrieveInformation method retrieves information about the USB device that is associated with a specified framework USB device object.
old-location: wdf\wdfusbtargetdeviceretrieveinformation.htm
old-project: wdf
ms.assetid: 68fc8d8b-3ba2-4f22-8a7e-29971a38544b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_dd8528c2-9697-4cc3-88f2-ba198fbe7594.xml, WdfUsbTargetDeviceRetrieveInformation, WdfUsbTargetDeviceRetrieveInformation method, kmdf.wdfusbtargetdeviceretrieveinformation, wdf.wdfusbtargetdeviceretrieveinformation, wdfusb/WdfUsbTargetDeviceRetrieveInformation
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfUsbTargetDeviceRetrieveInformation
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceRetrieveInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceRetrieveInformation</b> method retrieves information about the USB device that is associated with a specified framework USB device object.


## -syntax


````
NTSTATUS WdfUsbTargetDeviceRetrieveInformation(
  _In_  WDFUSBDEVICE                UsbDevice,
  _Out_ PWDF_USB_DEVICE_INFORMATION Information
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Information [out]

A pointer to a caller-allocated <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_information.md">WDF_USB_DEVICE_INFORMATION</a> structure that receives USB device information.


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
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbTargetDeviceRetrieveInformation</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

In framework versions 1.11 and later, the driver  can call <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicequeryusbcapability.md">WdfUsbTargetDeviceQueryUsbCapability</a> to retrieve a device's operating speed.


#### Examples

The following code example is part of an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function that creates a USB device object, initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_information.md">WDF_USB_DEVICE_INFORMATION</a> structure, and calls <b>WdfUsbTargetDeviceRetrieveInformation</b>. 

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
    if (pMyDeviceContext-&gt;UsbDevice != NULL) {
        return STATUS_SUCCESS;
    }

    WDF_USB_DEVICE_CREATE_CONFIG_INIT(
                                      &amp;Config,
                                      USBD_CLIENT_CONTRACT_VERSION_602
                                      );

    status = WdfUsbTargetDeviceCreateWithParameters(
                                      Device,
                                      &amp;Config,
                                      WDF_NO_OBJECT_ATTRIBUTES,
                                      &amp;pMyDeviceContext-&gt;UsbDevice
                                      );
    if (!NT_SUCCESS(status)) {
        return status;
    }

    WDF_USB_DEVICE_INFORMATION_INIT(&amp;deviceInfo);

    status = WdfUsbTargetDeviceRetrieveInformation(
                                      pDeviceContext-&gt;UsbDevice, 
                                      &amp;deviceInfo
                                      );
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicequeryusbcapability.md">WdfUsbTargetDeviceQueryUsbCapability</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_information.md">WDF_USB_DEVICE_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceRetrieveInformation method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

