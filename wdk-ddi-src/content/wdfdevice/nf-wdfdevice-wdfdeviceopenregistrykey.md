---
UID: NF:wdfdevice.WdfDeviceOpenRegistryKey
title: WdfDeviceOpenRegistryKey function (wdfdevice.h)
description: The WdfDeviceOpenRegistryKey method opens a device's hardware key or a driver's software key in the registry and creates a framework registry-key object that represents the registry key.
old-location: wdf\wdfdeviceopenregistrykey.htm
tech.root: wdf
ms.assetid: 0ccae1e9-23d4-44cd-ae5a-985490db1d86
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_ab116304-7951-4b19-b197-3943a4a415db.xml, WdfDeviceOpenRegistryKey, WdfDeviceOpenRegistryKey method, kmdf.wdfdeviceopenregistrykey, wdf.wdfdeviceopenregistrykey, wdfdevice/WdfDeviceOpenRegistryKey
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: AccessHardwareKey, DriverCreate, KmdfIrql, KmdfIrql2
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
- WdfDeviceOpenRegistryKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceOpenRegistryKey function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceOpenRegistryKey</b> method opens a device's hardware key or a driver's software key in the registry and creates a framework registry-key object that represents the registry key.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DeviceInstanceKeyType [in]

Specifies which key or subkey to open.  This is a bitwise OR of the following flags (which are defined in <i>Wdm.h</i>).

<table>
<tr>
<th>DeviceInstanceKeyType flag</th>
<th>Meaning</th>
<th>Framework</th>
</tr>
<tr>
<td>
<b>PLUGPLAY_REGKEY_DEVICE</b>

</td>
<td>
Opens the <b>Device Parameters</b> subkey under the device's hardware key.

</td>
<td>KMDF/UMDF</td>
</tr>
<tr>
<td>
<b>PLUGPLAY_REGKEY_DRIVER</b>

</td>
<td>
 Opens the driver's software key. A UMDF driver that sets this flag must also set <i>DesiredAccess</i> to <b>KEY_READ</b>.  Otherwise this method returns <b>STATUS_ACCESS_DENIED</b>.

</td>
<td>KMDF/UMDF</td>
</tr>
<tr>
<td>
<b>PLUGPLAY_REGKEY_CURRENT_HWPROFILE</b>

</td>
<td>
 A KMDF driver uses this  flag to  open the copy of the hardware or software key that is in the current hardware profile.

</td>
<td>KMDF</td>
</tr>
<tr>
<td>
<b>PLUGPLAY_REGKEY_DRIVER | WDF_REGKEY_DRIVER_SUBKEY</b>

</td>
<td>
 A UMDF  driver uses these flags together to  open the <b>ServiceName</b> subkey of the driver's software key for read/write access.

</td>
<td>UMDF</td>
</tr>
<tr>
<td>
<b>PLUGPLAY_REGKEY_DEVICE | WDF_REGKEY_DEVICE_SUBKEY</b>

</td>
<td>
Similarly, a UMDF driver uses these flags to open the <b>ServiceName</b> subkey of the device's hardware key for read/write access.

</td>
<td>UMDF</td>
</tr>
</table>
 


### -param DesiredAccess [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>-typed value that specifies access rights that the driver is requesting for the specified registry key.

A KMDF driver typically requests <b>KEY_READ</b>, <b>KEY_WRITE</b>, or <b>KEY_READ | KEY_WRITE</b>.

If you are writing a UMDF driver, use the following table.

<table>
<tr>
<th>DeviceInstanceKeyType</th>
<th>DesiredAccess</th>
</tr>
<tr>
<td>
<b>PLUGPLAY_REGKEY_DEVICE</b>

</td>
<td>
<b>KEY_READ</b>

</td>
</tr>
<tr>
<td>
<b>PLUGPLAY_REGKEY_DEVICE | WDF_REGKEY_DEVICE_SUBKEY</b>

</td>
<td>
<b>KEY_READ</b> or <b>KEY_READ | KEY_SET_VALUE</b>

</td>
</tr>
<tr>
<td>
<b>PLUGPLAY_REGKEY_DRIVER</b>

</td>
<td>
<b>KEY_READ</b>

</td>
</tr>
<tr>
<td>
<b>PLUGPLAY_REGKEY_DRIVER | WDF_REGKEY_DRIVER_SUBKEY</b>

</td>
<td>
<b>KEY_READ</b> or <b>KEY_READ | KEY_SET_VALUE</b>

</td>
</tr>
</table>
 

As a best practice, ask for only the types of access that your driver needs.


### -param KeyAttributes [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Key [out]

A pointer to a location that receives a handle to the new registry-key object.


## -returns



<b>WdfDeviceOpenRegistryKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceopenregistrykey">WdfDeviceOpenRegistryKey</a> was not called at IRQL = PASSIVE_LEVEL. 

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
 

For a list of other return values that the <b>WdfDeviceOpenRegistryKey</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



If your driver must open a hardware or software key before it has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitopenregistrykey">WdfFdoInitOpenRegistryKey</a> instead of <b>WdfDeviceOpenRegistryKey</b>.

When the driver has finished using the registry key that it opened with <b>WdfDeviceOpenRegistryKey</b>, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryclose">WdfRegistryClose</a>.

For more information about the registry, hardware and software keys, and registry objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

For code examples that use <b>WdfDeviceOpenRegistryKey</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistrycreatekey">WdfRegistryCreateKey</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryopenkey">WdfRegistryOpenKey</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfregistry/nf-wdfregistry-wdfregistryqueryvalue">WdfRegistryQueryValue</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitopenregistrykey">WdfFdoInitOpenRegistryKey</a>
 

 

