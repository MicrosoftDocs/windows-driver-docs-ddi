---
UID: NF:wdfdevice.WdfDeviceOpenDevicemapKey
title: WdfDeviceOpenDevicemapKey function (wdfdevice.h)
description: The WdfDeviceOpenDevicemapKey method opens the DEVICEMAP key and creates a framework registry-key object that represents the registry key.
old-location: wdf\wdfdeviceopendevicemapkey.htm
tech.root: wdf
ms.assetid: EAFC6B53-98E9-46A4-9D45-56B0A32993B1
ms.date: 02/26/2018
keywords: ["WdfDeviceOpenDevicemapKey function"]
ms.keywords: WdfDeviceOpenDevicemapKey, WdfDeviceOpenDevicemapKey method, wdf.wdfdeviceopendevicemapkey, wdfdevice/WdfDeviceOpenDevicemapKey
f1_keywords:
 - "wdfdevice/WdfDeviceOpenDevicemapKey"
 - "WdfDeviceOpenDevicemapKey"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
- WdfDeviceOpenDevicemapKey
targetos: Windows
req.typenames: 
---

# WdfDeviceOpenDevicemapKey function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceOpenDevicemapKey</b> method opens the <b>DEVICEMAP</b> key and creates a framework registry-key object that represents the registry key.


## -parameters




### -param Device 
[in]
A handle to a framework device object.


### -param KeyName 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that specifies the name of the subkey to open under <b>DEVICEMAP</b>.


### -param DesiredAccess 
[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>-typed value that specifies access rights that the driver is requesting for the specified registry key.

A KMDF driver typically requests <b>KEY_READ</b>, <b>KEY_WRITE</b>, or <b>KEY_READ | KEY_WRITE</b>.

A UMDF driver typically requests <b>KEY_READ</b> or <b>KEY_SET_VALUE</b>.


### -param KeyAttributes 
[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Key 
[out]
A pointer to a location that receives a handle to the new registry-key object.  The 


## -returns



<b>WdfDeviceOpenDevicemapKey</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceopendevicemapkey">WdfDeviceOpenDevicemapKey</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified. For UMDF, this return value can indicate insufficient access rights.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A registry-key object could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The specified registry key does not exist.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfDeviceOpenDevicemapKey</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



The registry contains a <b>HKEY_LOCAL_MACHINE\HARDWARE\DEVICEMAP</b> key that some drivers for older technologies, such as serial and parallel ports, use. If your driver supports a technology that uses the <b>DEVICEMAP</b> key, the driver can access subkeys and values under the key by calling <b>WdfDeviceOpenDevicemapKey</b>.

<b>WdfDeviceOpenDevicemapKey</b> returns a volatile <i>Key</i>. This means that the information is not preserved when the corresponding registry hive is unloaded.

When the driver has finished using the registry key that it opened with <b>WdfDeviceOpenDevicemapKey</b>, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfregistry/nf-wdfregistry-wdfregistryclose">WdfRegistryClose</a>.

For more information about the registry, hardware and software keys, and registry objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceopenregistrykey">WdfDeviceOpenRegistryKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitopenregistrykey">WdfFdoInitOpenRegistryKey</a>
 

 

