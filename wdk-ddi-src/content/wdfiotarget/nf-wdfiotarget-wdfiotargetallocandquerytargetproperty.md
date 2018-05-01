---
UID: NF:wdfiotarget.WdfIoTargetAllocAndQueryTargetProperty
title: WdfIoTargetAllocAndQueryTargetProperty function
author: windows-driver-content
description: The WdfIoTargetAllocAndQueryTargetProperty method allocates a buffer and retrieves a specified device property for a specified I/O target.
old-location: wdf\wdfiotargetallocandquerytargetproperty.htm
old-project: wdf
ms.assetid: 9b66ba25-7723-4805-aa7c-7091a18d749b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_f92747ac-d6f3-444f-a76b-91503a0db3a3.xml, WdfIoTargetAllocAndQueryTargetProperty, WdfIoTargetAllocAndQueryTargetProperty method, kmdf.wdfiotargetallocandquerytargetproperty, wdf.wdfiotargetallocandquerytargetproperty, wdfiotarget/WdfIoTargetAllocAndQueryTargetProperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfIoTargetAllocAndQueryTargetProperty
product: Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetAllocAndQueryTargetProperty function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoTargetAllocAndQueryTargetProperty</b> method allocates a buffer and retrieves a specified device property for a specified I/O target.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a> or from a method that a specialized I/O target supplies.


### -param DeviceProperty [in]

A <a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a>-typed value that identifies the device property to be retrieved.


### -param PoolType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>-typed value that specifies the type of memory to be allocated.


### -param PropertyMemoryAttributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that the function will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


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
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfIoTargetAllocAndQueryTargetProperty</b> method determines the amount of memory that is necessary to hold the requested device property. This method allocates enough memory to hold the data and returns a handle to a framework memory object that describes the allocated memory. To access the data, your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>.

For more information about <b>WdfIoTargetAllocAndQueryTargetProperty</b>, see <a href="https://msdn.microsoft.com/70ae920e-de2d-4014-bae4-74058b26e7c0">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example calls <b>WdfIoTargetAllocAndQueryTargetProperty</b> to obtain the <b>DevicePropertyFriendlyName</b> property. After <b>WdfIoTargetAllocAndQueryTargetProperty</b> returns, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a> to obtain a pointer to the buffer that contains the name string.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFMEMORY  targetName;
NTSTATUS  status;

status = WdfIoTargetAllocAndQueryTargetProperty(
                                                Target,
                                                DevicePropertyFriendlyName,
                                                NonPagedPool,
                                                WDF_NO_OBJECT_ATTRIBUTES,
                                                &amp;targetName
                                                );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545882">WdfDeviceAllocAndQueryProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548646">WdfIoTargetQueryTargetProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>
 

 

