---
UID: NF:wdm.IoGetDeviceInterfaces
title: IoGetDeviceInterfaces function
author: windows-driver-content
description: The IoGetDeviceInterfaces routine returns a list of device interface instances of a particular device interface class (such as all devices on the system that support a HID interface).
old-location: kernel\iogetdeviceinterfaces.htm
old-project: kernel
ms.assetid: a980fe92-ccd9-4a23-b324-ae8ef4e10345
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoGetDeviceInterfaces
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
req.alt-api: IoGetDeviceInterfaces
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetDeviceInterfaces function



## -description
The <b>IoGetDeviceInterfaces</b> routine returns a list of device interface instances of a particular device interface class (such as all devices on the system that support a HID interface).



## -syntax

````
NTSTATUS IoGetDeviceInterfaces(
  _In_     const GUID           *InterfaceClassGuid,
  _In_opt_       PDEVICE_OBJECT PhysicalDeviceObject,
  _In_           ULONG          Flags,
  _Out_          PWSTR          *SymbolicLinkList
);
````


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

A driver typically sets the DEVICE_INTERFACE_INCLUDE_NONACTIVE flag to locate disabled interface instances that the driver must enable. For example, the class installer for the device might have been directed by the INF file to register one or more interface instances for the device. The interface instances would be registered but are not usable until they are enabled by the driver (using <a href="..\wdm\nf-wdm-iosetdeviceinterfacestate.md">IoSetDeviceInterfaceState</a>). To narrow the list of interface instances returned to only those exposed by a given device, a driver can specify a <i>PhysicalDeviceObject</i>.


### -param SymbolicLinkList [out]

A pointer to a wide character pointer to which the routine, if successful, writes the base address of a buffer that contains a list of Unicode strings. These strings are symbolic link names that identify the device interface instances that match the search criteria. Each Unicode string in the list is null-terminated; the end of the whole list is marked by an additional null character. The routine allocates the buffer for these strings from paged system memory. The caller is responsible for freeing the buffer (by calling the <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a> routine) when it is no longer needed.

If no device interface instances match the search criteria, this routine returns STATUS_SUCCESS and the string contains a single NULL character.


## -returns
<b>IoGetDeviceInterfaces</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>Possibly indicates that <i>PhysicalDeviceObject</i> was not a valid PDO pointer.

 


## -remarks
<b>IoGetDeviceInterfaces</b> returns a list of device interface instances that match the search criteria. A kernel-mode component typically calls this routine to get a list of all enabled device interface instances of a particular device interface class. Such a component can get a pointer to the file object and/or the device object for an interface by calling the <a href="..\wdm\nf-wdm-iogetdeviceobjectpointer.md">IoGetDeviceObjectPointer</a> or <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> routine. The device object pointer returned by <b>IoGetDeviceObjectPointer</b> points to the top of the device stack for the device and can be used in calls to the <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a> routine.

If there is a default interface for the requested device interface class, it is listed first in <i>SymbolicLinkList</i>. Default interfaces can be set by user mode, but not by kernel mode.

The format of a symbolic link name is opaque; the caller should not attempt to parse a symbolic link name.

Symbolic links for device interface instances can be used across system boots.

To be notified when additional device interface instances of a particular class are enabled on the system, register for notification of a device class change by calling the <a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a> routine.

Callers of <b>IoGetDeviceInterfaces</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iogetdeviceobjectpointer.md">IoGetDeviceObjectPointer</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioregisterdeviceinterface.md">IoRegisterDeviceInterface</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iosetdeviceinterfacestate.md">IoSetDeviceInterfaceState</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetDeviceInterfaces routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

