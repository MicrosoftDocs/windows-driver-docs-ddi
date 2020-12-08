---
UID: NF:wdfdevice.WdfDeviceRetrieveDeviceInterfaceString
title: WdfDeviceRetrieveDeviceInterfaceString function (wdfdevice.h)
description: The WdfDeviceRetrieveDeviceInterfaceString method retrieves the symbolic link name that the operating system assigned to a device interface that the driver registered for a specified device.
old-location: wdf\wdfdeviceretrievedeviceinterfacestring.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDeviceRetrieveDeviceInterfaceString function"]
ms.keywords: DFDeviceObjectGeneralRef_a7f98bd1-23e0-4461-9a6c-481b8e10ba63.xml, WdfDeviceRetrieveDeviceInterfaceString, WdfDeviceRetrieveDeviceInterfaceString method, kmdf.wdfdeviceretrievedeviceinterfacestring, wdf.wdfdeviceretrievedeviceinterfacestring, wdfdevice/WdfDeviceRetrieveDeviceInterfaceString
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceRetrieveDeviceInterfaceString
 - wdfdevice/WdfDeviceRetrieveDeviceInterfaceString
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
 - WdfDeviceRetrieveDeviceInterfaceString
---

# WdfDeviceRetrieveDeviceInterfaceString function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceRetrieveDeviceInterfaceString</b> method retrieves the symbolic link name that the operating system assigned to a device interface that the driver registered for a specified device.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param InterfaceClassGUID 

[in]
A pointer to a GUID that identifies the device interface class.

### -param ReferenceString 

[in, optional]
A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that describes a reference string for the device interface. This parameter is optional and can be <b>NULL</b> if the driver did not specify a reference string when it called <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreatedeviceinterface">WdfDeviceCreateDeviceInterface</a>.

### -param String 

[in]
A handle to a <a href="/windows-hardware/drivers/wdf/using-string-objects">framework string object</a>. The framework will assign the symbolic link name's Unicode string to the string object.

## -returns

<b>WdfDeviceRetrieveDeviceInterfaceString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceretrievedeviceinterfacestring">WdfDeviceRetrieveDeviceInterfaceString</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The specified device object was initialized by <a href="/windows-hardware/drivers/ddi/wdfcontrol/nf-wdfcontrol-wdfcontroldeviceinitallocate">WdfControlDeviceInitAllocate</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
A device interface that matches the specified GUID and reference string could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The driver called <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreatedeviceinterface">WdfDeviceCreateDeviceInterface</a> but the system has not yet assigned a symbolic link name to the device interface.

</td>
</tr>
</table>
 

<b>WdfDeviceRetrieveDeviceInterfaceString</b> might also return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about device interfaces, see <a href="/windows-hardware/drivers/wdf/using-device-interfaces">Using Device Interfaces</a>.


#### Examples

The following code example creates a string object and then retrieves a specified device interface's symbolic link name. 

```cpp
NTSTATUS status;
WDFSTRING string;

status = WdfStringCreate(
                         NULL,
                         WDF_NO_OBJECT_ATTRIBUTES,
                         &string
                         );
if (NT_SUCCESS(status)) {
    status = WdfDeviceRetrieveDeviceInterfaceString(
                         Device,
                         &GUID_DEVINTERFACE_DDI_TEST1,
                         NULL,
                         string
                         );
    if (!NT_SUCCESS(status)) {
        return status;
    }
}
```

## -see-also

<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="/windows-hardware/drivers/ddi/wdfcontrol/nf-wdfcontrol-wdfcontroldeviceinitallocate">WdfControlDeviceInitAllocate</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreatedeviceinterface">WdfDeviceCreateDeviceInterface</a>



<a href="/windows-hardware/drivers/ddi/wdfstring/nf-wdfstring-wdfstringcreate">WdfStringCreate</a>
