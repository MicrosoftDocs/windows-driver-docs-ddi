---
UID: NF:wdfdevice.WdfDeviceRetrieveDeviceName
title: WdfDeviceRetrieveDeviceName function (wdfdevice.h)
description: The WdfDeviceRetrieveDeviceName method returns the device name for a specified device.
old-location: wdf\wdfdeviceretrievedevicename.htm
tech.root: wdf
ms.assetid: 26fdc802-e28b-47a0-b248-5403d024fea3
ms.date: 02/26/2018
keywords: ["WdfDeviceRetrieveDeviceName function"]
ms.keywords: DFDeviceObjectGeneralRef_8c3bab28-12f1-456b-a972-37444e81c847.xml, WdfDeviceRetrieveDeviceName, WdfDeviceRetrieveDeviceName method, kmdf.wdfdeviceretrievedevicename, wdf.wdfdeviceretrievedevicename, wdfdevice/WdfDeviceRetrieveDeviceName
f1_keywords:
 - "wdfdevice/WdfDeviceRetrieveDeviceName"
req.header: wdfdevice.h
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
- WdfDeviceRetrieveDeviceName
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceRetrieveDeviceName function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceRetrieveDeviceName</b> method returns the device name for a specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param String [in]

A handle to a framework string object that receives the device name.


## -returns



If the operation succeeds, <b>WdfDeviceRetrieveDeviceName</b> returns STATUS_SUCCESS. Additional return values include:

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
An invalid parameter was detected.

</td>
</tr>
</table>
 

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



The <b>WdfDeviceRetrieveDeviceName</b> method returns the device name that the driver specified in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignname">WdfDeviceInitAssignName</a>.

To obtain the device name string from the string object, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfstring/nf-wdfstring-wdfstringgetunicodestring">WdfStringGetUnicodeString</a>.


#### Examples

The following code example creates a string object and then retrieves a specified device's name. 

```cpp
NTSTATUS status;
WDFSTRING string;

status = WdfStringCreate(
                         NULL,
                         WDF_NO_OBJECT_ATTRIBUTES,
                         &string
                         );
if (NT_SUCCESS(status)) {
    status = WdfDeviceRetrieveDeviceName(
                                         Device,
                                         string
                                         );
    if (!NT_SUCCESS(status)) {
        return status;
    }
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignname">WdfDeviceInitAssignName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicequeryproperty">WdfDeviceQueryProperty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfstring/nf-wdfstring-wdfstringcreate">WdfStringCreate</a>
 

 

