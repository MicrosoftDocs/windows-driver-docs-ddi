---
UID: NF:wdm.IoRegisterDeviceInterface
title: IoRegisterDeviceInterface function
description: The IoRegisterDeviceInterface routine registers a device interface class, if it has not been previously registered, and creates a new instance of the interface class, which a driver can subsequently enable for use by applications or other system components.
old-location: kernel\ioregisterdeviceinterface.htm
tech.root: kernel
ms.assetid: 4d0782c7-0516-4326-9994-7820446f2af6
ms.date: 04/30/2018
ms.keywords: IoRegisterDeviceInterface, IoRegisterDeviceInterface routine [Kernel-Mode Driver Architecture], k104_4916c641-8510-425d-953f-68ed7a3f8976.xml, kernel.ioregisterdeviceinterface, wdm/IoRegisterDeviceInterface
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoRegisterDeviceInterface function


## -description


The <b>IoRegisterDeviceInterface</b> routine registers a [device interface class](https://docs.microsoft.com/windows-hardware/drivers/install/device-interface-classes), if it has not been previously registered, and creates a new instance of the interface class, which a driver can subsequently enable for use by applications or other system components.


## -parameters




### -param PhysicalDeviceObject [in]

A pointer to the PDO for the device.


### -param InterfaceClassGuid [in]

A pointer to the class GUID that identifies the functionality (the device interface class) being registered.


### -param ReferenceString [in, optional]

Optionally points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>. The string must not contain any path separator characters ("/" or "\\"). Function drivers typically specify <b>NULL</b> for this parameter. Filter drivers must specify <b>NULL</b>.

Reference strings are only used by a few bus drivers, such as <i>swenum</i>, which is a bus driver that uses device interface instances as placeholders for software devices created on demand. When an instance of an interface is opened, the I/O manager passes the instance's reference string to the driver. The string becomes part of the interface instance's name (as an appended path component). The driver can then use the reference string to differentiate between two interface instances of the same class for a single device.

On Microsoft Windows 98/Me systems, the <i>ReferenceString</i> value can be no longer than MAX_PATH characters. There is no length limit on Windows 2000 and later versions of Windows.


### -param SymbolicLinkName [out]

A pointer to a Unicode string structure allocated by the caller. If this routine is successful, it initializes the Unicode string and allocates the string buffer containing the kernel-mode path to the symbolic link for an instance of the specified device interface class. 

The caller must treat <i>SymbolicLinkName</i> as opaque and must not disassemble it.

The caller is responsible for freeing <i>SymbolicLinkName</i> with <a href="https://msdn.microsoft.com/library/windows/hardware/ff561903">RtlFreeUnicodeString</a> when it is no longer needed.


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

If the device interface class has not been registered previously, the I/O manager creates a registry key for it, along with instance-specific persistent storage under the key. Drivers can access this persistent storage using <a href="https://msdn.microsoft.com/library/windows/hardware/ff549433">IoOpenDeviceInterfaceRegistryKey</a>.

A driver registers an interface instance once and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549700">IoSetDeviceInterfaceState</a> to enable and disable the interface.

Registered interfaces persist across operating system reboots. If the specified interface is already registered, the I/O manager passes its name in <i>SymbolicLinkName </i>and returns the informational success status STATUS_OBJECT_NAME_EXISTS.

Most drivers use a <b>NULL</b> reference string for a device interface instance. If a driver uses a non-<b>NULL</b> reference string, it must do additional work, including possibly managing its own namespace and security. A filter driver that exposes a device interface must use a <b>NULL</b> <i>ReferenceString</i> to avoid conflicts with other drivers in the device stack.

Callers of this routine are not required to remove the registration for a device interface when it is no longer needed. Device interface registrations can be removed from user mode, if necessary.

Callers of <b>IoRegisterDeviceInterface</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549186">IoGetDeviceInterfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549433">IoOpenDeviceInterfaceRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549700">IoSetDeviceInterfaceState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561903">RtlFreeUnicodeString</a>
 

 

