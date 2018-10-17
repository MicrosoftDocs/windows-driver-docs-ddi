---
UID: NF:wdm.IoGetDeviceInterfaces
title: IoGetDeviceInterfaces function
author: windows-driver-content
description: The IoGetDeviceInterfaces routine returns a list of device interface instances of a particular device interface class (such as all devices on the system that support a HID interface).
old-location: kernel\iogetdeviceinterfaces.htm
tech.root: kernel
ms.assetid: a980fe92-ccd9-4a23-b324-ae8ef4e10345
ms.date: 4/30/2018
ms.keywords: IoGetDeviceInterfaces, IoGetDeviceInterfaces routine [Kernel-Mode Driver Architecture], k104_c4286fdb-9b4e-42e4-a1f6-fb3a79d556a7.xml, kernel.iogetdeviceinterfaces, wdm/IoGetDeviceInterfaces
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	IoGetDeviceInterfaces
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetDeviceInterfaces function


## -description


The <b>IoGetDeviceInterfaces</b> routine returns a list of device interface instances of a particular device interface class (such as all devices on the system that support a HID interface).


## -parameters




### -param InterfaceClassGuid [in]

Pointer to a class GUID specifying the device interface class. The GUIDs for a class should be in a device-specific header file. 


### -param PhysicalDeviceObject [in, optional]

Pointer to an optional PDO that narrows the search to only the device interface instances of the device represented by the PDO. 


### -param Flags [in]

Specifies flags that modify the search for device interfaces. Only one flag is currently defined, and is described in the following table.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DEVICE_INTERFACE_INCLUDE_NONACTIVE

</td>
<td>
Return disabled device interface instances in addition to enabled interface instances.

</td>
</tr>
</table>
 

When searching for a device that supports a particular interface class, the caller requires an enabled interface instance and thus does not set the DEVICE_INTERFACE_INCLUDE_NONACTIVE flag.

A driver typically sets the DEVICE_INTERFACE_INCLUDE_NONACTIVE flag to locate disabled interface instances that the driver must enable. For example, the class installer for the device might have been directed by the INF file to register one or more interface instances for the device. The interface instances would be registered but are not usable until they are enabled by the driver (using <a href="https://msdn.microsoft.com/library/windows/hardware/ff549700">IoSetDeviceInterfaceState</a>). To narrow the list of interface instances returned to only those exposed by a given device, a driver can specify a <i>PhysicalDeviceObject</i>.


### -param SymbolicLinkList [out]

A pointer to a wide character pointer to which the routine, if successful, writes the base address of a buffer that contains a list of Unicode strings. These strings are symbolic link names that identify the device interface instances that match the search criteria. Each Unicode string in the list is null-terminated; the end of the whole list is marked by an additional null character. The routine allocates the buffer for these strings from paged system memory. The caller is responsible for freeing the buffer (by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a> routine) when it is no longer needed.

If no device interface instances match the search criteria, this routine returns STATUS_SUCCESS and the string contains a single NULL character.


## -returns



<b>IoGetDeviceInterfaces</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following.

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
Possibly indicates that <i>PhysicalDeviceObject</i> was not a valid PDO pointer.

</td>
</tr>
</table>
 




## -remarks



<b>IoGetDeviceInterfaces</b> returns a list of device interface instances that match the search criteria. A kernel-mode component typically calls this routine to get a list of all enabled device interface instances of a particular device interface class. Such a component can get a pointer to the file object and/or the device object for an interface by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549198">IoGetDeviceObjectPointer</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a> routine. The device object pointer returned by <b>IoGetDeviceObjectPointer</b> points to the top of the device stack for the device and can be used in calls to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a> routine.

If there is a default interface for the requested device interface class, it is listed first in <i>SymbolicLinkList</i>. Default interfaces can be set by user mode, but not by kernel mode.

The format of a symbolic link name is opaque; the caller should not attempt to parse a symbolic link name.

Symbolic links for device interface instances can be used across system boots.

To be notified when additional device interface instances of a particular class are enabled on the system, register for notification of a device class change by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549526">IoRegisterPlugPlayNotification</a> routine.

Callers of <b>IoGetDeviceInterfaces</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549198">IoGetDeviceObjectPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549506">IoRegisterDeviceInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549526">IoRegisterPlugPlayNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549700">IoSetDeviceInterfaceState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>
 

 

