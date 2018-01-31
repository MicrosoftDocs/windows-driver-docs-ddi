---
UID: NF:wdffdo.WdfFdoInitOpenRegistryKey
title: WdfFdoInitOpenRegistryKey function
author: windows-driver-content
description: The WdfFdoInitOpenRegistryKey method opens a device's hardware key or a driver's software key in the registry and creates a framework registry-key object that represents the registry key.
old-location: wdf\wdffdoinitopenregistrykey.htm
old-project: wdf
ms.assetid: 1b720e3e-8858-4567-ada3-30ac0dcf9696
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdffdoinitopenregistrykey, DFDeviceObjectFdoPdoRef_8768fe63-0134-467f-9610-0cdaf018f784.xml, WdfFdoInitOpenRegistryKey, kmdf.wdffdoinitopenregistrykey, wdffdo/WdfFdoInitOpenRegistryKey, WdfFdoInitOpenRegistryKey method
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfFdoInitOpenRegistryKey
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WdfFdoInitOpenRegistryKey function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfFdoInitOpenRegistryKey</b> method opens a device's hardware key or a driver's software key in the registry and creates a framework registry-key object that represents the registry key.


## -syntax


````
NTSTATUS WdfFdoInitOpenRegistryKey(
  _In_     PWDFDEVICE_INIT        DeviceInit,
  _In_     ULONG                  DeviceInstanceKeyType,
  _In_     ACCESS_MASK            DesiredAccess,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES KeyAttributes,
  _Out_    WDFKEY                 *Key
);
````


## -parameters




#### - DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.


#### - DeviceInstanceKeyType [in]

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


#### - DesiredAccess [in]

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


#### - KeyAttributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


#### - Key [out]

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

<a href="..\wdffdo\nf-wdffdo-wdffdoinitopenregistrykey.md">WdfFdoInitOpenRegistryKey</a> was not called at IRQL = PASSIVE_LEVEL. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified, or the driver did not obtain the WDFDEVICE_INIT structure from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For UMDF, this return value can indicate insufficient access rights.

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


The driver must call <b>WdfFdoInitOpenRegistryKey</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about the <b>WdfFdoInitOpenRegistryKey</b> method, see <a href="https://msdn.microsoft.com/3b988f6d-c50e-412d-85cb-031746535ff4">Creating Device Objects in a Function Driver</a>.

or more information about the registry, hardware and software keys, and registry objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceopenregistrykey.md">WdfDeviceOpenRegistryKey</a>

<a href="..\wdfdriver\nf-wdfdriver-wdfdriveropenparametersregistrykey.md">WdfDriverOpenParametersRegistryKey</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoInitOpenRegistryKey method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

