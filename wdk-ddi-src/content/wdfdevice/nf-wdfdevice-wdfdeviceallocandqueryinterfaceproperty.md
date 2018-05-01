---
UID: NF:wdfdevice.WdfDeviceAllocAndQueryInterfaceProperty
title: WdfDeviceAllocAndQueryInterfaceProperty function
author: windows-driver-content
description: The WdfDeviceAllocAndQueryInterfaceProperty method allocates a buffer and retrieves a specified device interface property.
old-location: wdf\wdfdeviceallocandqueryinterfaceproperty.htm
old-project: wdf
ms.assetid: 40516E83-892C-4538-B452-DAB0F5ACBB25
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDeviceAllocAndQueryInterfaceProperty, WdfDeviceAllocAndQueryInterfaceProperty method, wdf.wdfdeviceallocandqueryinterfaceproperty, wdfdevice/WdfDeviceAllocAndQueryInterfaceProperty
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
-	WdfDeviceAllocAndQueryInterfaceProperty
product: Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceAllocAndQueryInterfaceProperty function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfDeviceAllocAndQueryInterfaceProperty</b> method  allocates a buffer and retrieves a specified device interface property.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PropertyData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265629">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a> structure that identifies the device interface property to be retrieved.


### -param PoolType [in]

A <b>POOL_TYPE</b>-typed enumerator that specifies the type of memory to be allocated.


### -param PropertyMemoryAttributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that the function will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param PropertyMemory [out]

A pointer to a <b>WDFMEMORY</b>-typed location that receives a handle to a framework memory object.




### -param Type [out]

A pointer to a <b>DEVPROPTYPE</b>-typed variable that, on return,  identifies the type of property data contained in <i>PropertyMemory</i>.


## -returns



If the <b>WdfDeviceAllocAndQueryInterfaceProperty</b> method encounters no errors, it returns STATUS_SUCCESS. Additional return values include:

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
One of the parameters is incorrect.

</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>WdfDeviceAllocAndQueryInterfaceProperty</b> method determines the amount of memory that is necessary to hold the requested device interface property. It allocates enough memory to hold the data, and returns a handle to a framework memory object that describes the allocated memory. To access the data, your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>. 

For information about related methods, see <a href="https://msdn.microsoft.com/C81988F9-E0DA-439F-B770-DAD86E33D5F3">Accessing the Unified Device Property Model</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265629">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265630">WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265600">WdfDeviceAssignInterfaceProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265607">WdfDeviceQueryInterfaceProperty</a>
 

 

