---
UID: NF:wdfdevice.WdfDeviceQueryProperty
title: WdfDeviceQueryProperty function (wdfdevice.h)
description: The WdfDeviceQueryProperty method retrieves a specified device property.
old-location: wdf\wdfdevicequeryproperty.htm
tech.root: wdf
ms.assetid: be05a5b5-e895-402b-bf0a-cbdb75fdef1d
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_e3f58989-ddd0-4402-94bf-418481869972.xml, WdfDeviceQueryProperty, WdfDeviceQueryProperty method, kmdf.wdfdevicequeryproperty, wdf.wdfdevicequeryproperty, wdfdevice/WdfDeviceQueryProperty
f1_keywords:
 - "wdfdevice/WdfDeviceQueryProperty"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
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
- WdfDeviceQueryProperty
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceQueryProperty function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceQueryProperty</b> method retrieves a specified device property.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DeviceProperty [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfwdm/ne-wudfwdm-device_registry_property">DEVICE_REGISTRY_PROPERTY</a>-typed enumerator that identifies the device property to be retrieved.


### -param BufferLength [in]

The size, in bytes, of the buffer that is pointed to by <i>PropertyBuffer</i>.


### -param PropertyBuffer [out]

A caller-supplied pointer to a caller-allocated buffer that receives the requested information. The pointer can be <b>NULL</b> if the <i>BufferLength</i> parameter is zero.


### -param ResultLength [out]

A caller-supplied location that, on return, contains the size, in bytes, of the information that the method stored in <i>PropertyBuffer</i>. If the function's return value is STATUS_BUFFER_TOO_SMALL, this location receives the required buffer size.


## -returns



If the operation succeeds, <b>WdfDeviceQueryProperty</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The supplied buffer is too small to receive the information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>DeviceProperty</i> value is invalid

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The device's drivers have not yet reported the device's properties.

</td>
</tr>
</table>
 

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Before receiving device property data, drivers typically call the <b>WdfDeviceQueryProperty</b> method just to obtain the required buffer size. For some properties, the data size can change between when the required size is returned and when the driver calls <b>WdfDeviceQueryProperty</b> again. Therefore, drivers should call <b>WdfDeviceQueryProperty</b> inside a loop that executes until the return status is not STATUS_BUFFER_TOO_SMALL. 

It is best to use <b>WdfDeviceQueryProperty</b> only if the required buffer size is known and unchanging, because in that case the driver has to call <b>WdfDeviceQueryProperty</b> only once. If the required buffer size is unknown or varies, the driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandqueryproperty">WdfDeviceAllocAndQueryProperty</a>. 

Alternatively, you can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicequerypropertyex">WdfDeviceQueryPropertyEx</a> to access device properties that are exposed through the Unified Property Model.


#### Examples

The following code example obtains a device's <b>DevicePropertyBusTypeGuid</b> property. The example calls <b>WdfDeviceQueryProperty</b> instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandqueryproperty">WdfDeviceAllocAndQueryProperty</a> because the length of a GUID is known.

```cpp
GUID  busTypeGuid;
ULONG  resultLength = 0;
NTSTATUS  status;

status = WdfDeviceQueryProperty( 
                                device,
                                DevicePropertyBusTypeGuid,
                                sizeof(GUID),
                                (PVOID)&busTypeGuid,
                                &resultLength
                                );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandqueryproperty">WdfDeviceAllocAndQueryProperty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitqueryproperty">WdfFdoInitQueryProperty</a>
 

 

