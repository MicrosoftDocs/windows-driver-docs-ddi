---
UID: NF:wdfdevice.WdfDeviceRetrieveDeviceInterfaceString
title: WdfDeviceRetrieveDeviceInterfaceString function
author: windows-driver-content
description: The WdfDeviceRetrieveDeviceInterfaceString method retrieves the symbolic link name that the operating system assigned to a device interface that the driver registered for a specified device.
old-location: wdf\wdfdeviceretrievedeviceinterfacestring.htm
old-project: wdf
ms.assetid: 97c67410-851c-4352-8ace-5738ab4332d2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_a7f98bd1-23e0-4461-9a6c-481b8e10ba63.xml, WdfDeviceRetrieveDeviceInterfaceString, WdfDeviceRetrieveDeviceInterfaceString method, kmdf.wdfdeviceretrievedeviceinterfacestring, wdf.wdfdeviceretrievedeviceinterfacestring, wdfdevice/WdfDeviceRetrieveDeviceInterfaceString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	WdfDeviceRetrieveDeviceInterfaceString
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceRetrieveDeviceInterfaceString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceRetrieveDeviceInterfaceString</b> method retrieves the symbolic link name that the operating system assigned to a device interface that the driver registered for a specified device.


## -syntax


````
NTSTATUS WdfDeviceRetrieveDeviceInterfaceString(
  _In_           WDFDEVICE        Device,
  _In_     const GUID             *InterfaceClassGUID,
  _In_opt_       PCUNICODE_STRING ReferenceString,
  _In_           WDFSTRING        String
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param InterfaceClassGUID [in]

A pointer to a GUID that identifies the device interface class.


### -param ReferenceString [in, optional]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that describes a reference string for the device interface. This parameter is optional and can be <b>NULL</b> if the driver did not specify a reference string when it called <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreatedeviceinterface.md">WdfDeviceCreateDeviceInterface</a>. 


### -param String [in]

A handle to a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-string-objects">framework string object</a>. The framework will assign the symbolic link name's Unicode string to the string object.


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

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceretrievedeviceinterfacestring.md">WdfDeviceRetrieveDeviceInterfaceString</a> was not called at IRQL = PASSIVE_LEVEL. 

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
The specified device object was initialized by <a href="..\wdfcontrol\nf-wdfcontrol-wdfcontroldeviceinitallocate.md">WdfControlDeviceInitAllocate</a>.

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
The driver called <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreatedeviceinterface.md">WdfDeviceCreateDeviceInterface</a> but the system has not yet assigned a symbolic link name to the device interface.

</td>
</tr>
</table>
 

<b>WdfDeviceRetrieveDeviceInterfaceString</b> might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



For more information about device interfaces, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces">Using Device Interfaces</a>.


#### Examples

The following code example creates a string object and then retrieves a specified device interface's symbolic link name. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS status;
WDFSTRING string;

status = WdfStringCreate(
                         NULL,
                         WDF_NO_OBJECT_ATTRIBUTES,
                         &amp;string
                         );
if (NT_SUCCESS(status)) {
    status = WdfDeviceRetrieveDeviceInterfaceString(
                         Device,
                         &amp;GUID_DEVINTERFACE_DDI_TEST1,
                         NULL,
                         string
                         );
    if (!NT_SUCCESS(status)) {
        return status;
    }
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfstring\nf-wdfstring-wdfstringcreate.md">WdfStringCreate</a>



<a href="..\wdfcontrol\nf-wdfcontrol-wdfcontroldeviceinitallocate.md">WdfControlDeviceInitAllocate</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreatedeviceinterface.md">WdfDeviceCreateDeviceInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceRetrieveDeviceInterfaceString method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

