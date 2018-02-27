---
UID: NF:wdm.IoRegisterDeviceInterface
title: IoRegisterDeviceInterface function
author: windows-driver-content
description: The IoRegisterDeviceInterface routine registers a device interface class, if it has not been previously registered, and creates a new instance of the interface class, which a driver can subsequently enable for use by applications or other system components.
old-location: kernel\ioregisterdeviceinterface.htm
old-project: kernel
ms.assetid: 4d0782c7-0516-4326-9994-7820446f2af6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoRegisterDeviceInterface, IoRegisterDeviceInterface routine [Kernel-Mode Driver Architecture], k104_4916c641-8510-425d-953f-68ed7a3f8976.xml, kernel.ioregisterdeviceinterface, wdm/IoRegisterDeviceInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive3, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoRegisterDeviceInterface
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoRegisterDeviceInterface function


## -description


The <b>IoRegisterDeviceInterface</b> routine registers a <a href="https://msdn.microsoft.com/C989D2D3-E8DE-4D64-86EE-3D3B3906390D">device interface class</a>, if it has not been previously registered, and creates a new instance of the interface class, which a driver can subsequently enable for use by applications or other system components.


## -syntax


````
NTSTATUS IoRegisterDeviceInterface(
  _In_           PDEVICE_OBJECT  PhysicalDeviceObject,
  _In_     const GUID            *InterfaceClassGuid,
  _In_opt_       PUNICODE_STRING ReferenceString,
  _Out_          PUNICODE_STRING SymbolicLinkName
);
````


## -parameters




### -param PhysicalDeviceObject [in]

A pointer to the PDO for the device.


### -param InterfaceClassGuid [in]

A pointer to the class GUID that identifies the functionality (the device interface class) being registered.


### -param ReferenceString [in, optional]

Optionally points to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>. The string must not contain any path separator characters ("/" or "\"). Function drivers typically specify <b>NULL</b> for this parameter. Filter drivers must specify <b>NULL</b>.

Reference strings are only used by a few bus drivers, such as <i>swenum</i>, which is a bus driver that uses device interface instances as placeholders for software devices created on demand. When an instance of an interface is opened, the I/O manager passes the instance's reference string to the driver. The string becomes part of the interface instance's name (as an appended path component). The driver can then use the reference string to differentiate between two interface instances of the same class for a single device.

On Microsoft Windows 98/Me systems, the <i>ReferenceString</i> value can be no longer than MAX_PATH characters. There is no length limit on Windows 2000 and later versions of Windows.


### -param SymbolicLinkName [out]

A pointer to a Unicode string structure allocated by the caller. If this routine is successful, it initializes the Unicode string and allocates the string buffer containing the kernel-mode path to the symbolic link for an instance of the specified device interface class. 

The caller must treat <i>SymbolicLinkName</i> as opaque and must not disassemble it.

The caller is responsible for freeing <i>SymbolicLinkName</i> with <a href="..\wudfwdm\nf-wudfwdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a> when it is no longer needed.


## -returns



<b>IoRegisterDeviceInterface</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following.

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
The parameters are invalid. Possibilities include that <i>PhysicalDeviceObject</i> does not point to a valid PDO, or that the <i>ReferenceString</i> string contains an invalid character. 

</td>
</tr>
</table>
 




## -remarks



<b>IoRegisterDeviceInterface</b> registers a device interface class, if it has not been previously registered, and creates a new instance of the interface class. A driver can call this routine several times for a given device to register several interface classes and create instances of the classes. A function or filter driver typically registers device interfaces in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine. For example, a fault-tolerant volume driver might register an instance of a fault-tolerant-volume interface and an instance of a volume interface for a particular volume.

If the device interface class has not been registered previously, the I/O manager creates a registry key for it, along with instance-specific persistent storage under the key. Drivers can access this persistent storage using <a href="..\wdm\nf-wdm-ioopendeviceinterfaceregistrykey.md">IoOpenDeviceInterfaceRegistryKey</a>.

A driver registers an interface instance once and then calls <a href="..\wdm\nf-wdm-iosetdeviceinterfacestate.md">IoSetDeviceInterfaceState</a> to enable and disable the interface.

Registered interfaces persist across operating system reboots. If the specified interface is already registered, the I/O manager passes its name in <i>SymbolicLinkName </i>and returns the informational success status STATUS_OBJECT_NAME_EXISTS.

Most drivers use a <b>NULL</b> reference string for a device interface instance. If a driver uses a non-<b>NULL</b> reference string, it must do additional work, including possibly managing its own namespace and security. A filter driver that exposes a device interface must use a <b>NULL</b> <i>ReferenceString</i> to avoid conflicts with other drivers in the device stack.

Callers of this routine are not required to remove the registration for a device interface when it is no longer needed. Device interface registrations can be removed from user mode, if necessary.

Callers of <b>IoRegisterDeviceInterface</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.




## -see-also

<a href="..\wdm\nf-wdm-iosetdeviceinterfacestate.md">IoSetDeviceInterfaceState</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>



<a href="..\wdm\nf-wdm-iogetdeviceinterfaces.md">IoGetDeviceInterfaces</a>



<a href="..\wdm\nf-wdm-ioopendeviceinterfaceregistrykey.md">IoOpenDeviceInterfaceRegistryKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRegisterDeviceInterface routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

