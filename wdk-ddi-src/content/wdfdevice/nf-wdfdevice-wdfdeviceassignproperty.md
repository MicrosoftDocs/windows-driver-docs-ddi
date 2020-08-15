---
UID: NF:wdfdevice.WdfDeviceAssignProperty
title: WdfDeviceAssignProperty function (wdfdevice.h)
description: The WdfDeviceAssignProperty method modifies the current setting of a device property.
old-location: wdf\wdfdeviceassignproperty.htm
tech.root: wdf
ms.assetid: 5110C452-53E6-401A-9D14-EBD95D3F8BE2
ms.date: 02/26/2018
keywords: ["WdfDeviceAssignProperty function"]
ms.keywords: WdfDeviceAssignProperty, WdfDeviceAssignProperty method, wdf.wdfdeviceassignproperty, wdfdevice/WdfDeviceAssignProperty
f1_keywords:
 - "wdfdevice/WdfDeviceAssignProperty"
 - "WdfDeviceAssignProperty"
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
- WdfDeviceAssignProperty
targetos: Windows
req.typenames: 
---

# WdfDeviceAssignProperty function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceAssignProperty</b> method modifies the current setting of a device property.


## -parameters




### -param Device 
[in]
A handle to a framework device object.


### -param DeviceProperty 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure that identifies the device property to modify.


### -param Type 
[in]
A <b>DEVPROPTYPE</b>-typed variable that specifies the type of the data stored in <i>Data</i>.


### -param Size 
[in]
The size, in bytes, of the buffer that is pointed to by <i>Data</i>.


### -param Data 
[in, optional]
A pointer to a caller-allocated buffer that contains the device property data. Set this parameter to <b>NULL</b> to delete the specified property.


## -returns



If the operation succeeds, <b>WdfDeviceAssignProperty</b> returns STATUS_SUCCESS. Additional return values include:

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
 

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



You can use <b>WdfDeviceAssignProperty</b> to modify the setting of any property that is exposed through the unified property model.

For information about related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-the-unified-device-property-model">Accessing the Unified Device Property Model</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceassigninterfaceproperty">WdfDeviceAssignInterfaceProperty</a>
 

 

