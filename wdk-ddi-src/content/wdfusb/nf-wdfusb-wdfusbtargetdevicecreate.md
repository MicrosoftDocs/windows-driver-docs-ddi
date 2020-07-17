---
UID: NF:wdfusb.WdfUsbTargetDeviceCreate
title: WdfUsbTargetDeviceCreate function (wdfusb.h)
description: The WdfUsbTargetDeviceCreate method creates a framework USB device object for a specified framework device object and opens the USB device for I/O operations.
old-location: wdf\wdfusbtargetdevicecreate.htm
tech.root: wdf
ms.assetid: 5a2d3430-ca94-42f0-bfeb-fd38d9d4958a
ms.date: 02/26/2018
keywords: ["WdfUsbTargetDeviceCreate function"]
ms.keywords: DFUsbRef_be9c210e-6cf0-4e0b-a5d5-f0b02d7a2141.xml, WdfUsbTargetDeviceCreate, WdfUsbTargetDeviceCreate method, kmdf.wdfusbtargetdevicecreate, wdf.wdfusbtargetdevicecreate, wdfusb/WdfUsbTargetDeviceCreate
f1_keywords:
 - "wdfusb/WdfUsbTargetDeviceCreate"
 - "WdfUsbTargetDeviceCreate"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbDeviceCreate, UsbDeviceCreateFail, UsbDeviceCreateTarget, UsbKmdfIrql, UsbKmdfIrql2
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
- WdfUsbTargetDeviceCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceCreate</b> method creates a framework USB device object for a specified framework device object and opens the USB device for I/O operations.
<div class="alert"><b>Note</b>  If you are building your driver using KMDF 1.11 or UMDF 2.0, or later, we recommend that you call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a> instead of  <b>WdfUsbTargetDeviceCreate</b>.</div><div> </div>

## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Attributes [in, optional]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new USB device object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param UsbDevice [out]

A pointer to a location that receives a handle to the new framework USB device object.


## -returns



<b>WdfUsbTargetDeviceCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
There was insufficient memory to create a new USB device object.

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
 

For a list of other return values that the <b>WdfUsbTargetDeviceCreate</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A driver that uses a USB I/O target must call <b>WdfUsbTargetDeviceCreate</b> after its device enters its working (D0) state. Typically, a driver calls <b>WdfUsbTargetDeviceCreate</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function. (The driver cannot call <b>WdfUsbTargetDeviceCreate</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.)

<b>WdfUsbTargetDeviceCreate</b> obtains the USB device descriptor and the first USB configuration descriptor from the device and stores them. It also creates a framework USB interface object for each interface in the device's first configuration. To determine the number of interfaces that the configuration supports, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetnuminterfaces">WdfUsbTargetDeviceGetNumInterfaces</a>.

After calling <b>WdfUsbTargetDeviceCreate</b>, your driver can call additional <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/">framework USB device object methods</a>.

The parent of each USB device object is the driver's framework driver object. The driver cannot change this parent, and the <b>ParentObject</b> member or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>.

For more information about the <b>WdfUsbTargetDeviceCreate</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example is part of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function that calls <b>WdfUsbTargetDeviceCreate</b>. The example stores the USB device object's handle in driver-defined context space. 

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

    pMyDeviceContext = GetDeviceContext(Device);

    // If object handle is not NULL, MyEvtDevicePrepareHardware
    // was called previously and the handle is still valid.
    if (pMyDeviceContext->UsbDevice != NULL) {
        return STATUS_SUCCESS;
    }
 status = WdfUsbTargetDeviceCreate(
                                      Device,
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetnuminterfaces">WdfUsbTargetDeviceGetNumInterfaces</a>
 

 

