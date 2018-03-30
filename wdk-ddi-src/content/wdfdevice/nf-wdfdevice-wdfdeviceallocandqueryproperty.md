---
UID: NF:wdfdevice.WdfDeviceAllocAndQueryProperty
title: WdfDeviceAllocAndQueryProperty function
author: windows-driver-content
description: The WdfDeviceAllocAndQueryProperty method allocates a buffer and retrieves a specified device property.
old-location: wdf\wdfdeviceallocandqueryproperty.htm
old-project: wdf
ms.assetid: f921fee7-e2c0-4e0f-a78b-d2dff8af97a2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_d093b9da-de6b-467d-a6bd-c25d7a4145f8.xml, WdfDeviceAllocAndQueryProperty, WdfDeviceAllocAndQueryProperty method, kmdf.wdfdeviceallocandqueryproperty, wdf.wdfdeviceallocandqueryproperty, wdfdevice/WdfDeviceAllocAndQueryProperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	WdfDeviceAllocAndQueryProperty
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceAllocAndQueryProperty function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceAllocAndQueryProperty</b> method allocates a buffer and retrieves a specified device property.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DeviceProperty [in]

A <a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a>-typed enumerator that identifies the device property to be retrieved.


### -param PoolType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>-typed enumerator that specifies the type of memory to be allocated.


### -param PropertyMemoryAttributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that the function will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param PropertyMemory [out]

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object. 


## -returns



If the operation succeeds, <b>WdfDeviceAllocAndQueryProperty</b> returns STATUS_SUCCESS. Additional return values include:

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
The device's drivers have not yet reported the device's properties.

</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



The <b>WdfDeviceAllocAndQueryProperty</b> method determines the amount of memory that is necessary to hold the requested device property. It allocates enough memory to hold the data, and returns a handle to a framework memory object that describes the allocated memory. To access the data, your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>. 

Alternatively, you can use <a href="https://msdn.microsoft.com/library/windows/hardware/dn265599">WdfDeviceAllocAndQueryPropertyEx</a> to access device properties that are exposed through the Unified Property Model.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure with attributes for the framework memory object that the framework will create for the requested property. Then, the example calls <b>WdfDeviceAllocAndQueryProperty</b> to obtain the <b>DevicePropertyPhysicalDeviceObjectName</b> property. After <b>WdfDeviceAllocAndQueryProperty</b> returns, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a> to obtain a pointer to the buffer that contains the name string.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  attributes;
NTSTATUS  status;
WDFDEVICE  device;
WDFMEMORY  memory;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.ParentObject = device;

status = WdfDeviceAllocAndQueryProperty(device,
                                        DevicePropertyPhysicalDeviceObjectName,
                                        NonPagedPool,
                                        &amp;attributes,
                                        &amp;memory
                                        );
if (!NT_SUCCESS(status)) {
    return STATUS_UNSUCCESSFUL;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546820">WdfDeviceQueryProperty</a>
 

 

