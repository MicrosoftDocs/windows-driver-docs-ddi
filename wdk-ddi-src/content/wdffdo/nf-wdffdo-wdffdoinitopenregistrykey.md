---
UID: NF:wdffdo.WdfFdoInitOpenRegistryKey
title: WdfFdoInitOpenRegistryKey function
author: windows-driver-content
description: The WdfFdoInitOpenRegistryKey method opens a device's hardware key or a driver's software key in the registry and creates a framework registry-key object that represents the registry key.
old-location: wdf\wdffdoinitopenregistrykey.htm
tech.root: wdf
ms.assetid: 1b720e3e-8858-4567-ada3-30ac0dcf9696
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_8768fe63-0134-467f-9610-0cdaf018f784.xml, WdfFdoInitOpenRegistryKey, WdfFdoInitOpenRegistryKey method, kmdf.wdffdoinitopenregistrykey, wdf.wdffdoinitopenregistrykey, wdffdo/WdfFdoInitOpenRegistryKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
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
-	WdfFdoInitOpenRegistryKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFdoInitOpenRegistryKey function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfFdoInitOpenRegistryKey</b> method opens a device's hardware key or a driver's software key in the registry and creates a framework registry-key object that represents the registry key.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.


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

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>-typed value that specifies access rights that the driver is requesting for the specified registry key.

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

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Key [out]

A pointer to a location that receives a handle to the new registry-key object.


## -returns



<b>WdfFdoInitOpenRegistryKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547249">WdfFdoInitOpenRegistryKey</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified, or the driver did not obtain the WDFDEVICE_INIT structure from its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function. For UMDF, this return value can indicate insufficient access rights.

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
 

For a list of other return values that the <b>WdfFdoInitOpenRegistryKey</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The driver must call <b>WdfFdoInitOpenRegistryKey</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about the <b>WdfFdoInitOpenRegistryKey</b> method, see <a href="https://msdn.microsoft.com/3b988f6d-c50e-412d-85cb-031746535ff4">Creating Device Objects in a Function Driver</a>.

or more information about the registry, hardware and software keys, and registry objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example opens a device's hardware key, with read access.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFKEY key;
NTSTATUS status;

status = WdfFdoInitOpenRegistryKey(
                                   DeviceInit,
                                   PLUGPLAY_REGKEY_DEVICE,
                                   GENERIC_READ,
                                   WDF_NO_OBJECT_ATTRIBUTES,
                                   &amp;key
                                   );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546804">WdfDeviceOpenRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547202">WdfDriverOpenParametersRegistryKey</a>
 

 

