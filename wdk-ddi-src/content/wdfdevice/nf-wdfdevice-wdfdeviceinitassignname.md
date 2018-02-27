---
UID: NF:wdfdevice.WdfDeviceInitAssignName
title: WdfDeviceInitAssignName function
author: windows-driver-content
description: The WdfDeviceInitAssignName method assigns a device name to a device's device object.
old-location: wdf\wdfdeviceinitassignname.htm
old-project: wdf
ms.assetid: 70b86a0f-a77d-4c79-931d-d0407083e5b0
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectGeneralRef_1acdbff1-2eb9-425c-91c8-aaa51f585d56.xml, WdfDeviceInitAssignName, WdfDeviceInitAssignName method, kmdf.wdfdeviceinitassignname, wdf.wdfdeviceinitassignname, wdfdevice/WdfDeviceInitAssignName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceInitAssignName
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitAssignName function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitAssignName</b> method assigns a device name to a device's device object.


## -syntax


````
NTSTATUS WdfDeviceInitAssignName(
  _In_     PWDFDEVICE_INIT  DeviceInit,
  _In_opt_ PCUNICODE_STRING DeviceName
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param DeviceName [in, optional]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that represents the device name.


## -returns



If <b>WdfDeviceInitAssignName</b> encounters no errors it returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The system cannot allocate space to store the device name.

</td>
</tr>
</table>
 




## -remarks



If a driver calls <b>WdfDeviceInitAssignName</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

If a driver calls <b>WdfDeviceInitAssignName</b> to assign a name, the driver can subsequently call <b>WdfDeviceInitAssignName</b> with a <b>NULL</b> <i>DeviceName</i> parameter to clear the device name. If the device name is <b>NULL</b> and the device object requires a name (because it represents a PDO or a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-control-device-objects">control device</a>), the operating system will create a name. 

For more information about naming device objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/controlling-device-access-in-kmdf-drivers">Controlling Device Access in Framework-Based Drivers</a>.

For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example assigns an <a href="https://msdn.microsoft.com/dfcc7338-7c4d-4b4c-9a13-c76bfe82f5a9">NT device name</a> to a device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DECLARE_CONST_UNICODE_STRING(MyDeviceName, L"\\Device\\Ramdisk") ;
status = WdfDeviceInitAssignName(
                                 DeviceInit,
                                 &amp;MyDeviceName
                                 );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceretrievedevicename.md">WdfDeviceRetrieveDeviceName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitAssignName method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

