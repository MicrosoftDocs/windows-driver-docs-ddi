---
UID: NF:wdfdevice.WdfDeviceAssignInterfaceProperty
title: WdfDeviceAssignInterfaceProperty function
author: windows-driver-content
description: The WdfDeviceAssignInterfaceProperty method modifies the current value of a device interface property.
old-location: wdf\wdfdeviceassigninterfaceproperty.htm
old-project: wdf
ms.assetid: 49608EE6-1666-4430-AD22-9627EEF6F223
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDeviceAssignInterfaceProperty, WdfDeviceAssignInterfaceProperty method, wdf.wdfdeviceassigninterfaceproperty, wdfdevice/WdfDeviceAssignInterfaceProperty
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
-	WdfDeviceAssignInterfaceProperty
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceAssignInterfaceProperty function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfDeviceAssignInterfaceProperty</b> method modifies the current value of a <a href="https://msdn.microsoft.com/43aa0ce6-a06b-43e4-a213-300554391ae0">device interface property</a>.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PropertyData [in]

A pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/dn265629">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a> structure.


### -param Type [in]

A <b>DEVPROPTYPE</b>-typed value that specifies the type of the data that is provided in <i>PropertyBuffer</i>.


### -param BufferLength [in]

Specifies the length, in bytes, of the buffer that <i>PropertyBuffer</i> points to.


### -param PropertyBuffer [in, optional]

A pointer to the device interface property data. Set this parameter to <b>NULL</b> to delete the specified property.


## -returns



If the <b>WdfDeviceAssignInterfaceProperty</b> method encounters no errors, it returns STATUS_SUCCESS. Additional return values include:

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



For information about related methods, see <a href="https://msdn.microsoft.com/C81988F9-E0DA-439F-B770-DAD86E33D5F3">Accessing the Unified Device Property Model</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265629">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a> structure and then calls <b>WdfDeviceAssignInterfaceProperty</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DEFINE_DEVPROPKEY(DEVPKEY_ToasterCrispLevelDword, 0x5d0ba64a, 0x2396, 0x4bc9, 0xbf, 0x49, 0x52, 0x1d, 0xa6, 0x2b, 0x1b, 0xed, 3);  // DEVPROP_TYPE_UINT32

ULONG crispLevel = 0;
WDF_DEVICE_INTERFACE_PROPERTY_DATA propertyData;

WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT(
                          &amp;propertyData, 
                          &amp;GUID_DEVINTERFACE_TOASTER_DRIVER
                          &amp;DEVPKEY_ToasterCrispLevelDword
                          );

status = WdfDeviceAssignInterfaceProperty(device, 
                                          &amp;propertData,
                                          DEVPROP_TYPE_UINT32,
                                          sizeof(crispLevel),
                                          &amp;crispLevel);
if (!NT_SUCCESS(status)) {
    return status;
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265629">WDF_DEVICE_INTERFACE_PROPERTY_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265630">WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265598">WdfDeviceAllocAndQueryInterfaceProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265607">WdfDeviceQueryInterfaceProperty</a>
 

 

