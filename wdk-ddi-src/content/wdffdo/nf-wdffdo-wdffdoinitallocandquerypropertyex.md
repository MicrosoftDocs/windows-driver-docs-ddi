---
UID: NF:wdffdo.WdfFdoInitAllocAndQueryPropertyEx
title: WdfFdoInitAllocAndQueryPropertyEx function
author: windows-driver-content
description: The WdfFdoInitAllocAndQueryPropertyEx method allocates a buffer and retrieves a specified device property.
old-location: wdf\wdffdoinitallocandquerypropertyex.htm
tech.root: wdf
ms.assetid: 8F338F5B-2F18-4D7D-AF96-7F80A48D37FB
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfFdoInitAllocAndQueryPropertyEx, WdfFdoInitAllocAndQueryPropertyEx method, wdf.wdffdoinitallocandquerypropertyex, wdffdo/WdfFdoInitAllocAndQueryPropertyEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
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
-	WdfFdoInitAllocAndQueryPropertyEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFdoInitAllocAndQueryPropertyEx function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfFdoInitAllocAndQueryPropertyEx</b> method allocates a buffer and retrieves a specified device property.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.


### -param DeviceProperty [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265632">WDF_DEVICE_PROPERTY_DATA</a> structure that identifies the device property to be retrieved.


### -param PoolType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>-typed enumerator that specifies the type of memory to be allocated.


### -param PropertyMemoryAttributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the memory object that the function will allocate. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param PropertyMemory [out]

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object. 


### -param Type [out]

A pointer to a <b>DEVPROPTYPE</b> variable. If the method is successful, upon return this parameter contains the property type value
                  of the property 
                  data stored in <i>PropertyMemory</i>.


## -returns



If the operation succeeds, <b>WdfFdoInitAllocAndQueryPropertyEx</b> returns STATUS_SUCCESS. Additional return values include:

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
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



The <b>WdfFdoInitAllocAndQueryPropertyEx</b> method determines the amount of memory that is necessary to hold the requested device interface property. It allocates enough memory to hold the data, and returns a handle to a framework memory object that describes the allocated memory. To access the data, your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>. 

The driver can call <b>WdfFdoInitAllocAndQueryPropertyEx</b> only before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

After calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>, a driver can obtain device property information by calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn265599">WdfDeviceAllocAndQueryPropertyEx</a>.

For information about related methods, see <a href="https://msdn.microsoft.com/C81988F9-E0DA-439F-B770-DAD86E33D5F3">Accessing the Unified Device Property Model</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547239">WdfFdoInitAllocAndQueryProperty</a>
 

 

