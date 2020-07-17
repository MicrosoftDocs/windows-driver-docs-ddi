---
UID: NF:wdfiotarget.WdfIoTargetAllocAndQueryTargetProperty
title: WdfIoTargetAllocAndQueryTargetProperty function (wdfiotarget.h)
description: The WdfIoTargetAllocAndQueryTargetProperty method allocates a buffer and retrieves a specified device property for a specified I/O target.
old-location: wdf\wdfiotargetallocandquerytargetproperty.htm
tech.root: wdf
ms.assetid: 9b66ba25-7723-4805-aa7c-7091a18d749b
ms.date: 02/26/2018
keywords: ["WdfIoTargetAllocAndQueryTargetProperty function"]
ms.keywords: DFIOTargetRef_f92747ac-d6f3-444f-a76b-91503a0db3a3.xml, WdfIoTargetAllocAndQueryTargetProperty, WdfIoTargetAllocAndQueryTargetProperty method, kmdf.wdfiotargetallocandquerytargetproperty, wdf.wdfiotargetallocandquerytargetproperty, wdfiotarget/WdfIoTargetAllocAndQueryTargetProperty
f1_keywords:
 - "wdfiotarget/WdfIoTargetAllocAndQueryTargetProperty"
 - "WdfIoTargetAllocAndQueryTargetProperty"
req.header: wdfiotarget.h
req.include-header: Wdf.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfIoTargetAllocAndQueryTargetProperty
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetAllocAndQueryTargetProperty function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoTargetAllocAndQueryTargetProperty</b> method allocates a buffer and retrieves a specified device property for a specified I/O target.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a> or from a method that a specialized I/O target supplies.


### -param DeviceProperty [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfwdm/ne-wudfwdm-device_registry_property">DEVICE_REGISTRY_PROPERTY</a>-typed value that identifies the device property to be retrieved.


### -param PoolType [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>-typed value that specifies the type of memory to be allocated.


### -param PropertyMemoryAttributes [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that the function will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param PropertyMemory [out]

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object. 


## -returns



<b>WdfIoTargetAllocAndQueryTargetProperty</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
The value that the <i>DeviceProperty</i> parameter specified was invalid.

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
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfIoTargetAllocAndQueryTargetProperty</b> method determines the amount of memory that is necessary to hold the requested device property. This method allocates enough memory to hold the data and returns a handle to a framework memory object that describes the allocated memory. To access the data, your driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>.

For more information about <b>WdfIoTargetAllocAndQueryTargetProperty</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/obtaining-information-about-a-general-i-o-target">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example calls <b>WdfIoTargetAllocAndQueryTargetProperty</b> to obtain the <b>DevicePropertyFriendlyName</b> property. After <b>WdfIoTargetAllocAndQueryTargetProperty</b> returns, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a> to obtain a pointer to the buffer that contains the name string.

```cpp
WDFMEMORY  targetName;
NTSTATUS  status;

status = WdfIoTargetAllocAndQueryTargetProperty(
                                                Target,
                                                DevicePropertyFriendlyName,
                                                NonPagedPool,
                                                WDF_NO_OBJECT_ATTRIBUTES,
                                                &targetName
                                                );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfwdm/ne-wudfwdm-device_registry_property">DEVICE_REGISTRY_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandqueryproperty">WdfDeviceAllocAndQueryProperty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetquerytargetproperty">WdfIoTargetQueryTargetProperty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>
 

 

