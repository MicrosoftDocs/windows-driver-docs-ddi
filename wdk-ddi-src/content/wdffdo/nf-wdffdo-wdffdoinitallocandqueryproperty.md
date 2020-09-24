---
UID: NF:wdffdo.WdfFdoInitAllocAndQueryProperty
title: WdfFdoInitAllocAndQueryProperty function (wdffdo.h)
description: The WdfFdoInitAllocAndQueryProperty method allocates a buffer and retrieves a specified device property.
old-location: wdf\wdffdoinitallocandqueryproperty.htm
tech.root: wdf
ms.assetid: 9c275d89-e01d-445b-8c60-ae5268cd28c3
ms.date: 02/26/2018
keywords: ["WdfFdoInitAllocAndQueryProperty function"]
ms.keywords: DFDeviceObjectFdoPdoRef_2de90bea-c2df-4aa7-b64f-b17df042268c.xml, WdfFdoInitAllocAndQueryProperty, WdfFdoInitAllocAndQueryProperty method, kmdf.wdffdoinitallocandqueryproperty, wdf.wdffdoinitallocandqueryproperty, wdffdo/WdfFdoInitAllocAndQueryProperty
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
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
 - WdfFdoInitAllocAndQueryProperty
 - wdffdo/WdfFdoInitAllocAndQueryProperty
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
 - WdfFdoInitAllocAndQueryProperty
---

# WdfFdoInitAllocAndQueryProperty function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfFdoInitAllocAndQueryProperty</b> method allocates a buffer and retrieves a specified device property.

## -parameters

### -param DeviceInit 

[in]
A pointer to a <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

### -param DeviceProperty 

[in]
A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-device_registry_property">DEVICE_REGISTRY_PROPERTY</a>-typed enumerator value that identifies the device property to be retrieved.

### -param PoolType 

[in]
A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>-typed enumerator value that specifies the type of memory to be allocated.

### -param PropertyMemoryAttributes 

[in, optional]
A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that <b>WdfFdoInitAllocAndQueryProperty</b> will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param PropertyMemory 

[out]
A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object.

## -returns

If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER or STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>DeviceProperty</i> value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure was not obtained from driver's <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

</td>
</tr>
</table>
 

The method might also return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

The driver must call <b>WdfFdoInitAllocAndQueryProperty</b> before calling <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

After calling <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>, a driver can obtain device property information by calling <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandqueryproperty">WdfDeviceAllocAndQueryProperty</a>.

For more information about the <b>WdfFdoInitAllocAndQueryProperty</b> method, see <a href="/windows-hardware/drivers/wdf/creating-device-objects-in-a-function-driver">Creating Device Objects in a Function Driver</a>.

Alternatively, you can use <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitallocandquerypropertyex">WdfFdoInitAllocAndQueryPropertyEx</a> to access device properties that are exposed through the Unified Property Model.


#### Examples

The following code example calls <b>WdfFdoInitAllocAndQueryProperty</b> to obtain a handle to a framework memory object that contains the name of a device's setup class. Then, the example calls <a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a> to obtain a pointer to the buffer that contains the setup class name's Unicode string.

```cpp
NTSTATUS  status = STATUS_SUCCESS;
PVOID  pMemoryBuffer = NULL;
WDFMEMORY  memory = NULL;

status = WdfFdoInitAllocAndQueryProperty(
                                         DeviceInit,
                                         DevicePropertyClassName, 
                                         NonPagedPool,
                                         WDF_NO_OBJECT_ATTRIBUTES,
                                         &memory
                                         );
if(NT_SUCCESS(status)){
 pMemoryBuffer = WdfMemoryGetBuffer(
                                    memory,
                                    NULL
                                    );
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandqueryproperty">WdfDeviceAllocAndQueryProperty</a>



<a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitqueryproperty">WdfFdoInitQueryProperty</a>