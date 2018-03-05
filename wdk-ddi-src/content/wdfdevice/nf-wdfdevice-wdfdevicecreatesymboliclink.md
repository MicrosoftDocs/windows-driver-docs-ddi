---
UID: NF:wdfdevice.WdfDeviceCreateSymbolicLink
title: WdfDeviceCreateSymbolicLink function
author: windows-driver-content
description: The WdfDeviceCreateSymbolicLink method creates a symbolic link to a specified device.
old-location: wdf\wdfdevicecreatesymboliclink.htm
old-project: wdf
ms.assetid: c22035a2-8ceb-42e9-9d54-8997ce0dd8da
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_f970bbdf-21d6-497c-abc1-84456c95dc79.xml, WdfDeviceCreateSymbolicLink, WdfDeviceCreateSymbolicLink method, kmdf.wdfdevicecreatesymboliclink, wdf.wdfdevicecreatesymboliclink, wdfdevice/WdfDeviceCreateSymbolicLink
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
-	WdfDeviceCreateSymbolicLink
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceCreateSymbolicLink function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceCreateSymbolicLink</b> method creates a symbolic link to a specified device.


## -syntax


````
NTSTATUS WdfDeviceCreateSymbolicLink(
  _In_ WDFDEVICE        Device,
  _In_ PCUNICODE_STRING SymbolicLinkName
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param SymbolicLinkName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a user-visible name for the device.


## -returns



If the operation succeeds, the <b>WdfDeviceCreateSymbolicLink</b> returns STATUS_SUCCCESS. Additional return values include:

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
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



If a driver creates a symbolic link for a device, applications can use the symbolic link name to access the device. Typically, instead of providing symbolic links, framework-based drivers provide <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces">device interfaces</a> that applications can use to access their devices.

If the device is removed unexpectedly (surprise-removed), the framework removes the symbolic link to the device. The driver can then use the symbolic link name for a new instance of the device.


#### Examples

The following code example from a KMDF driver creates an <a href="https://msdn.microsoft.com/9be6da8f-0641-4a67-9443-8e2056335bef">MS-DOS device name</a> that an application can use to access a device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define DOS_DEVICE_NAME  L"\\DosDevices\\MyDevice"
DECLARE_CONST_UNICODE_STRING(dosDeviceName, DOS_DEVICE_NAME);
NTSTATUS  status;

status = WdfDeviceCreateSymbolicLink(
                                     controlDevice,
                                     &amp;dosDeviceName
                                     );
if (!NT_SUCCESS(status)) {
    goto Error;
}</pre>
</td>
</tr>
</table></span></div>
A UMDF driver must provide a symbolic link name in the global <b>DosDevices</b> namespace, as the following code example illustrates.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define DOS_DEVICE_NAME  L"\\DosDevices\\Global\\MyDevice"
DECLARE_CONST_UNICODE_STRING(dosDeviceName, DOS_DEVICE_NAME);
NTSTATUS  status;

status = WdfDeviceCreateSymbolicLink(
                                     controlDevice,
                                     &amp;dosDeviceName
                                     );
if (!NT_SUCCESS(status)) {
    goto Error;
}</pre>
</td>
</tr>
</table></span></div>
For information about global and local <b>\DosDevices</b> namespaces, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554302">Local and Global MS-DOS Device Names</a>.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceCreateSymbolicLink method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

