---
UID: NF:wdfdevice.WdfDeviceOpenDevicemapKey
title: WdfDeviceOpenDevicemapKey function
author: windows-driver-content
description: The WdfDeviceOpenDevicemapKey method opens the DEVICEMAP key and creates a framework registry-key object that represents the registry key.
old-location: wdf\wdfdeviceopendevicemapkey.htm
old-project: wdf
ms.assetid: EAFC6B53-98E9-46A4-9D45-56B0A32993B1
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , D, K, O, W, WdfDeviceOpenDevicemapKey, WdfDeviceOpenDevicemapKey method, a, c, d, e, f, i, m, n, p, v, wdf.wdfdeviceopendevicemapkey, wdfdevice/WdfDeviceOpenDevicemapKey, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	WdfDeviceOpenDevicemapKey
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceOpenDevicemapKey function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceOpenDevicemapKey</b> method opens the <b>DEVICEMAP</b> key and creates a framework registry-key object that represents the registry key.


## -syntax


````
NTSTATUS WdfDeviceOpenDevicemapKey(
  _In_     WDFDEVICE              Device,
  _In_     PCUNICODE_STRING       KeyName,
  _In_     ACCESS_MASK            DesiredAccess,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES KeyAttributes,
  _Out_    WDFKEY                 *Key
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param KeyName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that specifies the name of the subkey to open under <b>DEVICEMAP</b>.


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>-typed value that specifies access rights that the driver is requesting for the specified registry key.

A KMDF driver typically requests <b>KEY_READ</b>, <b>KEY_WRITE</b>, or <b>KEY_READ | KEY_WRITE</b>.

A UMDF driver typically requests <b>KEY_READ</b> or <b>KEY_SET_VALUE</b>.


### -param KeyAttributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new registry-key object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Key [out]

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

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceopendevicemapkey.md">WdfDeviceOpenDevicemapKey</a> was not called at IRQL = PASSIVE_LEVEL. 

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
 

For a list of other return values that the <b>WdfDeviceOpenDevicemapKey</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



The registry contains a <b>HKEY_LOCAL_MACHINE\HARDWARE\DEVICEMAP</b> key that some drivers for older technologies, such as serial and parallel ports, use. If your driver supports a technology that uses the <b>DEVICEMAP</b> key, the driver can access subkeys and values under the key by calling <b>WdfDeviceOpenDevicemapKey</b>.

<b>WdfDeviceOpenDevicemapKey</b> returns a volatile <i>Key</i>. This means that the information is not preserved when the corresponding registry hive is unloaded.

When the driver has finished using the registry key that it opened with <b>WdfDeviceOpenDevicemapKey</b>, the driver must call <a href="..\wdfregistry\nf-wdfregistry-wdfregistryclose.md">WdfRegistryClose</a>.

For more information about the registry, hardware and software keys, and registry objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.




## -see-also

<a href="..\wdffdo\nf-wdffdo-wdffdoinitopenregistrykey.md">WdfFdoInitOpenRegistryKey</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceopenregistrykey.md">WdfDeviceOpenRegistryKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceOpenDevicemapKey method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

