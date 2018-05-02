---
UID: NF:wdfdevice.WdfDeviceQueryInterfaceProperty
title: WdfDeviceQueryInterfaceProperty function
author: windows-driver-content
description: The WdfDeviceQueryInterfaceProperty method retrieves a specified device interface property.
old-location: wdf\wdfdevicequeryinterfaceproperty.htm
old-project: wdf
ms.assetid: 0A09990B-DAB9-41D3-80BF-38CD6AF39625
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDeviceQueryInterfaceProperty, WdfDeviceQueryInterfaceProperty method, wdf.wdfdevicequeryinterfaceproperty, wdfdevice/WdfDeviceQueryInterfaceProperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfDeviceQueryInterfaceProperty
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceQueryInterfaceProperty function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfDeviceQueryInterfaceProperty</b> method retrieves a specified device interface property.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PropertyData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265629">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a> structure that identifies the device interface property to be retrieved.


### -param BufferLength [in]

The size, in bytes, of the buffer that is pointed to by <i>PropertyBuffer.</i>


### -param PropertyBuffer [out]

A pointer to a caller-allocated buffer that receives the requested device interface property. The pointer can be NULL if the <i>BufferLength</i> parameter is zero.


### -param ResultLength [out]

A caller-supplied location that, on return, contains the size, in bytes, of the information that <b>WdfDeviceQueryInterfaceProperty</b> stored in <i>PropertyBuffer</i>. If the function's return value is <b>STATUS_BUFFER_TOO_SMALL</b>, this location receives the required buffer size.


### -param Type [out]

A pointer to a <b>DEVPROPTYPE</b>-typed variable that identifies the type of property data that <b>WdfDeviceQueryInterfaceProperty</b> stored in the buffer that <i>PropertyBuffer</i> points to.


## -returns



If the <b>WdfDeviceQueryInterfaceProperty</b> method encounters no errors, it returns STATUS_SUCCESS. Additional return values include:

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
The input buffer is too small to receive the information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The specified parameter value is invalid.

</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



Before receiving device property data, drivers typically call the <b>WdfDeviceQueryInterfaceProperty</b> method just to obtain the required buffer size. For some properties, the data size can change between when the required size is returned and when the driver calls <b>WdfDeviceQueryInterfaceProperty</b> again. Therefore, drivers should call <b>WdfDeviceQueryInterfaceProperty</b> inside a loop that executes until the return status is not STATUS_BUFFER_TOO_SMALL. 

It is best to use <b>WdfDeviceQueryInterfaceProperty</b> only if the required buffer size is known and unchanging, because in that case the driver has to call <b>WdfDeviceQueryInterfaceProperty</b> only once. If the required buffer size is unknown or varies, the driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/dn265598">WdfDeviceAllocAndQueryInterfaceProperty</a>. 

For information about related methods, see <a href="https://msdn.microsoft.com/C81988F9-E0DA-439F-B770-DAD86E33D5F3">Accessing the Unified Device Property Model</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265629">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265630">WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265598">WdfDeviceAllocAndQueryInterfaceProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265600">WdfDeviceAssignInterfaceProperty</a>
 

 

