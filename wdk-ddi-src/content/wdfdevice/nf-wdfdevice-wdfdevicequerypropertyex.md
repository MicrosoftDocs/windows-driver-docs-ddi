---
UID: NF:wdfdevice.WdfDeviceQueryPropertyEx
title: WdfDeviceQueryPropertyEx function (wdfdevice.h)
description: The WdfDeviceQueryPropertyEx method retrieves a specified device property.
old-location: wdf\wdfdevicequerypropertyex.htm
tech.root: wdf
ms.assetid: CA189010-0BEB-420A-BE69-5F7FEE322FE3
ms.date: 02/26/2018
ms.keywords: WdfDeviceQueryPropertyEx, WdfDeviceQueryPropertyEx method, wdf.wdfdevicequerypropertyex, wdfdevice/WdfDeviceQueryPropertyEx
ms.topic: function
f1_keywords:
 - "wdfdevice/WdfDeviceQueryPropertyEx"
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
- WdfDeviceQueryPropertyEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceQueryPropertyEx function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceQueryPropertyEx</b> method retrieves a specified device property.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DeviceProperty [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure that identifies the device property to be retrieved.


### -param BufferLength [in]

The size, in bytes, of the buffer that is pointed to by <i>PropertyBuffer</i>.


### -param PropertyBuffer [out]

A caller-supplied pointer to a caller-allocated buffer that receives the requested information. The pointer can be <b>NULL</b> if the <i>BufferLength</i> parameter is zero.


### -param RequiredSize [out]

A caller-supplied location that, on return, contains the size, in bytes, of the information that the method stored in <i>PropertyBuffer</i>. If the function's return value is <b>STATUS_BUFFER_TOO_SMALL</b>, this location receives the required buffer size.


### -param Type [out]

A pointer to a <b>DEVPROPTYPE</b> variable. If the method is successful, upon return this parameter contains the property type value
                  of the property 
                  data stored in <i>PropertyBuffer</i>.


## -returns



If the operation succeeds, <b>WdfDeviceQueryPropertyEx</b> returns STATUS_SUCCESS. Additional return values include:

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



You can use <b>WdfDeviceQueryPropertyEx</b> to retrieve any property that is exposed through the unified property model, whereas the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicequeryproperty">WdfDeviceQueryProperty</a> method only allows querying a subset of the unified property model.

Before receiving device property data, drivers typically call the <b>WdfDeviceQueryPropertyEx</b> method just to obtain the required buffer size. For some properties, the data size can change between when the required size is returned and when the driver calls <b>WdfDeviceQueryPropertyEx</b> again. Therefore, drivers should call <b>WdfDeviceQueryPropertyEx</b> inside a loop that executes until the return status is not STATUS_BUFFER_TOO_SMALL. 

It is best to use <b>WdfDeviceQueryPropertyEx</b> only if the required buffer size is known and unchanging, because in that case the driver has to call <b>WdfDeviceQueryPropertyEx</b> only once. If the required buffer size is unknown or varies, the driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceallocandquerypropertyex">WdfDeviceAllocAndQueryPropertyEx</a>. 

For information about related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-the-unified-device-property-model">Accessing the Unified Device Property Model</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicequeryinterfaceproperty">WdfDeviceQueryInterfaceProperty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicequeryproperty">WdfDeviceQueryProperty</a>
 

 

