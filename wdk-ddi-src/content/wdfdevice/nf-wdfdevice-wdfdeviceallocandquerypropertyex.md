---
UID: NF:wdfdevice.WdfDeviceAllocAndQueryPropertyEx
title: WdfDeviceAllocAndQueryPropertyEx function (wdfdevice.h)
description: The WdfDeviceAllocAndQueryPropertyEx method allocates a buffer and retrieves a specified device property.
old-location: wdf\wdfdeviceallocandquerypropertyex.htm
tech.root: wdf
ms.assetid: 1C1AE0F6-2CAB-4983-B1A7-E6C8BA822754
ms.date: 02/26/2018
keywords: ["WdfDeviceAllocAndQueryPropertyEx function"]
ms.keywords: WdfDeviceAllocAndQueryPropertyEx, WdfDeviceAllocAndQueryPropertyEx method, wdf.wdfdeviceallocandquerypropertyex, wdfdevice/WdfDeviceAllocAndQueryPropertyEx
f1_keywords:
 - "wdfdevice/WdfDeviceAllocAndQueryPropertyEx"
 - "WdfDeviceAllocAndQueryPropertyEx"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: APC_LEVEL
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
- WdfDeviceAllocAndQueryPropertyEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceAllocAndQueryPropertyEx function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceAllocAndQueryPropertyEx</b> method allocates a buffer and retrieves a specified device property.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DeviceProperty [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure that identifies the device property to be retrieved.


### -param PoolType [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>-typed enumerator that specifies the type of memory to be allocated.


### -param PropertyMemoryAttributes [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that the function will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param PropertyMemory [out]

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object. 


### -param Type [out]

A pointer to a <b>DEVPROPTYPE</b> variable. If the method is successful, upon return this parameter contains the property type value
                  of the property 
                  data stored in <i>PropertyMemory</i>.


## -returns



If the operation succeeds, <b>WdfDeviceAllocAndQueryPropertyEx</b> returns STATUS_SUCCESS. Additional return values include:

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
The specified <i>DeviceProperty</i> value is invalid.


</td>
</tr>
</table>
 

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



You can use <b>WdfDeviceAllocAndQueryPropertyEx</b> to retrieve any property that is exposed through the unified property model, whereas the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandqueryproperty">WdfDeviceAllocAndQueryProperty</a> method only allows querying a subset of the unified property model.

The <b>WdfDeviceAllocAndQueryPropertyEx</b> method determines the amount of memory that is necessary to hold the requested device interface property. It allocates enough memory to hold the data, and returns a handle to a framework memory object that describes the allocated memory. To access the data, your driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>.

For information about related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-the-unified-device-property-model">Accessing the Unified Device Property Model</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandqueryinterfaceproperty">WdfDeviceAllocAndQueryInterfaceProperty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandqueryproperty">WdfDeviceAllocAndQueryProperty</a>
 

 

