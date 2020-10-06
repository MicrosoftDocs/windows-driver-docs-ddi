---
UID: NF:wdfminiport.WdfDeviceMiniportCreate
title: WdfDeviceMiniportCreate function (wdfminiport.h)
description: The WdfDeviceMiniportCreate method creates a framework device object that a miniport driver can use.
old-location: wdf\wdfdeviceminiportcreate.htm
tech.root: wdf
ms.assetid: d74dedbd-f418-4ea3-ae76-c0da9c5f2fb9
ms.date: 02/26/2018
keywords: ["WdfDeviceMiniportCreate function"]
ms.keywords: DFDeviceObjectGeneralRef_18104589-c58d-4e8b-af91-c6620b3772e9.xml, WdfDeviceMiniportCreate, WdfDeviceMiniportCreate method, kmdf.wdfdeviceminiportcreate, wdf.wdfdeviceminiportcreate, wdfminiport/WdfDeviceMiniportCreate
req.header: wdfminiport.h
req.include-header: Wdfminiport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceMiniportCreate
 - wdfminiport/WdfDeviceMiniportCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceMiniportCreate
---

# WdfDeviceMiniportCreate function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceMiniportCreate</b> method creates a framework device object that a miniport driver can use.

## -parameters

### -param Driver 

[in]
A handle to the driver's framework driver object, obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a>.

### -param Attributes 

[in, optional]
A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param DeviceObject 

[in]
A pointer to a WDM <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents the functional device object (FDO) for the miniport driver.

### -param AttachedDeviceObject 

[in, optional]
A pointer to a WDM DEVICE_OBJECT structure that represents the next-lower device object in the device stack.

### -param Pdo 

[in, optional]
A pointer to a WDM DEVICE_OBJECT structure that represents the physical device object (PDO) for the device.

### -param Device 

[out]
A pointer to a location that receives a handle to the new framework device object.

## -returns

If the <b>WdfDeviceMiniportCreate</b> method encounters no errors, it returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A device object could not be allocated.

</td>
</tr>
</table>
 

For a list of other return values that <b>WdfDeviceMiniportCreate</b> can return, see <a href="/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

The method might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

If your miniport driver uses the framework, the miniport driver should call <b>WdfDeviceMiniportCreate</b> when its port driver informs it that a device is available. Miniport drivers do not call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

Your miniport driver might receive its <i>DeviceObject</i>, <i>AttachedDeviceObject</i>, and <i>PDO</i> pointers from its port driver. For example, an NDIS miniport driver can obtain these pointers by calling <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismgetdeviceproperty">NdisMGetDeviceProperty</a>.

The following restrictions apply to framework device objects that a miniport driver obtains by calling <b>WdfDeviceMiniportCreate</b>:

<ul>
<li>
The device that the device object represents must support Plug and Play.

</li>
<li>
The device object does not support any of the device object's event callback functions. Therefore, the port driver must handle all Plug and Play (PnP) and power management operations. 

</li>
<li>
The device object handle cannot be passed to <a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a>, so the port driver must provide any required support for Windows Management Instrumentation (WMI).

</li>
<li>
The device object handle cannot be passed to <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>, so the framework does not support I/O queues for miniport drivers.

</li>
<li>
The device object handle cannot be passed to <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>, so the framework does not support interrupt objects for miniport drivers.

</li>
<li>
The device object handle cannot be passed to any general framework device object methods except <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>, <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmgetdeviceobject">WdfDeviceWdmGetDeviceObject</a>, <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmgetattacheddevice">WdfDeviceWdmGetAttachedDevice</a>, and <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmgetphysicaldevice">WdfDeviceWdmGetPhysicalDevice</a>.

</li>
<li>
The device object handle cannot be passed to any <a href="/windows-hardware/drivers/ddi/wdfdevice/">framework FDO methods</a> except <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoqueryforinterface">WdfFdoQueryForInterface</a>.

</li>
<li>
The device object handle cannot be passed to any <a href="/windows-hardware/drivers/ddi/wdfdevice/">framework PDO methods</a> or to <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>, so the miniport driver cannot be a bus driver.

</li>
<li>
The driver must eventually call <a href="/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a> to delete the device object that <b>WdfDeviceMiniportCreate</b> creates.

</li>
</ul>
Framework device objects that <b>WdfDeviceMiniportCreate</b> create can be used as a parent object for any subsequently created framework object. 

In order to send I/O requests to I/O targets, the miniport driver might pass the device object handle to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>, <a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>, or <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.

The miniport driver can pass the device object handle to <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a> if the device supports DMA operations.

For more information about miniport drivers, see <a href="/windows-hardware/drivers/wdf/creating-kmdf-miniport-drivers">Using Kernel-Mode Driver Framework with Miniport Drivers</a>.


#### Examples

The following code example calls <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismgetdeviceproperty">NdisMGetDeviceProperty</a> to obtain <i>DeviceObject</i>, <i>AttachedDeviceObject</i>, and <i>PDO</i> pointers; initializes the device object's context space, and creates a miniport device object. 

```cpp
WDF_OBJECT_ATTRIBUTES  ObjectAttributes;

NdisMGetDeviceProperty(
                       MiniportAdapterHandle,
                       &Adapter->Pdo,
                       &Adapter->Fdo,
                       &Adapter->NextDeviceObject,
                       NULL,
                       NULL
                       );
WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(
                                        &ObjectAttributes,
                                        WDF_DEVICE_INFO
                                        );
ntStatus = WdfDeviceMiniportCreate(
                                   WdfGetDriver(),
                                   &ObjectAttributes,
                                   Adapter->Fdo,
                                   Adapter->NextDeviceObject,
                                   Adapter->Pdo,
                                   &Adapter->WdfDevice
                                   );
if (!NT_SUCCESS (ntStatus)) {
    Status = NDIS_STATUS_FAILURE;
    break;
}
```

## -see-also

<a href="/windows-hardware/drivers/wdf/wdf-object-attributes-init-context-type">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfminiport/nf-wdfminiport-wdfdriverminiportunload">WdfDriverMiniportUnload</a>