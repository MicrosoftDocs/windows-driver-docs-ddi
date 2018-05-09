---
UID: NS:wdm._DEVICE_OBJECT
title: "_DEVICE_OBJECT"
author: windows-driver-content
description: A device object represents a logical, virtual, or physical device for which a driver handles I/O requests.
old-location: kernel\device_object.htm
old-project: kernel
ms.assetid: f3522315-cf15-41f7-ac87-c625c7dc8040
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PDEVICE_OBJECT, DEVICE_OBJECT, DEVICE_OBJECT structure [Kernel-Mode Driver Architecture], PDEVICE_OBJECT, PDEVICE_OBJECT structure pointer [Kernel-Mode Driver Architecture], _DEVICE_OBJECT, kernel.device_object, kstruct_a_93734fb2-0dd1-4376-a595-44008eb68f2c.xml, wdm/DEVICE_OBJECT, wdm/PDEVICE_OBJECT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	DEVICE_OBJECT
product:
- Windows
targetos: Windows
req.typenames: DEVICE_OBJECT, *PDEVICE_OBJECT
---

# _DEVICE_OBJECT structure


## -description


The <b>DEVICE_OBJECT</b> structure is used by the operating system to represent a device object. A device object represents a logical, virtual, or physical device for which a driver handles I/O requests.


## -struct-fields




### -field Type

Used by the operating system to indicate that an object is a device object. For device objects, the value of this member is 3. This is a read-only member.


### -field Size

Specifies the size, in bytes, of the device object. This size includes the driver-specified device extension pointed to by the <b>DeviceExtension</b> member, but does not include the opaque device object extension pointed to by the <b>DeviceObjectExtension</b> member. <b>Size</b> is a read-only member.


### -field ReferenceCount

Used by the I/O manager to track the number of open handles for the device that are associated with the device object. This allows the I/O manager to avoid unloading a driver when there are outstanding handles for the driver's device(s). This is a read-only member.


### -field DriverObject

A pointer to the driver object (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>), that represents the loaded image of the driver that was input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routines. This member is set by the I/O manager upon a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548407">IoCreateDeviceSecure</a>. This is a read-only member.


### -field NextDevice

A pointer to the next device object, if any, that was created by the same driver. The I/O manager updates this list at each successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548407">IoCreateDeviceSecure</a>.

A non- Plug and Play (PnP) driver that is being unloaded must traverse ("walk") the list of its device objects and delete them. A PnP driver does not have to walk this list of device objects. Instead, PnP drivers perform their cleanup during the device removal PnP operation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>).

A driver that recreates its device objects dynamically also uses this member. This is a read/write member.


### -field AttachedDevice

A pointer to the attached device object. If there is no attached device object, this member is <b>NULL</b>. The device object that is pointed to by the <b>AttachedDevice</b> member typically is the device object of a filter driver, which intercepts I/O requests originally targeted to the device represent by the device object. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548294">IoAttachDevice</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff548298">IoAttachDeviceByPointer</a> topics. This is an opaque member.


### -field CurrentIrp

A pointer to the current IRP if the driver has a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine whose entry point was set in the driver object and if the driver is currently processing IRP(s). Otherwise, this member is <b>NULL</b>. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550370">IoStartPacket</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550358">IoStartNextPacket</a> topics. This is a read-only member.


### -field Timer

A pointer to a timer object. This allows the I/O manager to call a driver-supplied timer routine every second. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549344">IoInitializeTimer</a>. This is a read/write member.


### -field Flags

Device drivers perform a bitwise <b>OR</b> operation with this member in their newly created device objects by using one or more of the following system-defined values:





#### DO_BUFFERED_IO or DO_DIRECT_IO

Specifies the type of buffering that is used by the I/O manager for I/O requests that are sent to the device stack. Higher-level drivers OR this member with the same value as the next-lower driver in the stack, except possibly for highest-level drivers.



#### DO_BUS_ENUMERATED_DEVICE

The operating system sets this flag in each physical device object (PDO). Drivers must not modify this flag.



#### DO_DEVICE_INITIALIZING

The I/O manager sets this flag when it creates the device object. A device function driver or filter driver clears the flag in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine, after it does the following:

<ul>
<li>Attaches the device object to the device stack.</li>
<li>Establishes the device power state.</li>
<li>Performs a bitwise OR operation on the member with one of the power flags (if it is necessary).</li>
</ul>
The Plug and Play (PnP) manager checks that the flag is clear after the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine returns.



#### DO_EXCLUSIVE

Indicates that the driver services an exclusive device, such as a video, serial, parallel, or sound device. WDM drivers must not set this flag. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563827">Specifying Exclusive Access to Device Objects</a> topic.



#### DO_MAP_IO_BUFFER

This flag is no longer used. Drivers should not set this flag.



#### DO_POWER_INRUSH

Drivers of devices that require inrush current when the device is turned on must set this flag. A driver cannot set both this flag and DO_POWER_PAGABLE.



#### DO_POWER_PAGABLE

Pageable drivers that are compatible with Microsoft Windows 2000 and later versions of Windows, are not part of the paging path, and do not require inrush current must set this flag. The system calls such drivers at IRQL = PASSIVE_LEVEL. Drivers cannot set both this flag and DO_POWER_INRUSH. All drivers for WDM, Microsoft Windows 98, and Windows Millennium Edition must set DO_POWER_PAGABLE.



#### DO_SHUTDOWN_REGISTERED

Used by the I/O manager to indicate that a driver has registered the device object for shutdown notifications. This flag should not be used by drivers.



#### DO_VERIFY_VOLUME

Removable-media drivers set this flag while they process transfer requests. Such drivers should also check for this flag in the target for a transfer request before they transfer any data. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a> topic.

For more information about how to set the <b>Flags</b> member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a>.


### -field Characteristics

Specifies one or more system-defined constants, combined with a bitwise OR operation, that provide additional information about the driver's device. These constants include the following:





#### FILE_AUTOGENERATED_DEVICE_NAME

Directs the I/O manager to generate a name for the device, instead of the caller specifying a <i>DeviceName</i> when it calls this routine. The I/O manager makes sure that the name is unique. This characteristic is typically specified by a PnP bus driver to generate a name for a physical device object (PDO) for a child device on the same bus. This characteristic is new starting with Microsoft Windows 2000 and Microsoft Windows 98.



#### FILE_CHARACTERISTIC_PNP_DEVICE

Indicates that the device object is part of a Plug and Play (PnP) stack. This characteristic is required if a bus driver (or bus filter driver) registers WMI support for a device object that has not yet received the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request. FILE_CHARACTERISTIC_PNP_DEVICE is also required if a function or filter driver registers for WMI <u>before</u> attaching to its device stack.



#### FILE_CHARACTERISTIC_TS_DEVICE

Indicates that the device object is part of a Terminal Services device stack. Drivers should not set this characteristic.



#### FILE_CHARACTERISTIC_WEBDAV_DEVICE

Indicates that a Web-based Distributed Authoring and Versioning (WebDAV) file system is mounted on the device. Drivers should not set this characteristic.



#### FILE_DEVICE_IS_MOUNTED

Indicates that a file system is mounted on the device. Drivers should not set this characteristic.



#### FILE_DEVICE_SECURE_OPEN

Directs the I/O manager to apply the security descriptor of the device object to relative opens and trailing file name opens for the device. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542068">Controlling Device Namespace Access</a> topic.



#### FILE_FLOPPY_DISKETTE

Indicates that the device is a floppy disk device.



#### FILE_READ_ONLY_DEVICE

Indicates that the device cannot be written to.



#### FILE_REMOTE_DEVICE

Indicates that the device is remote.



#### FILE_REMOVABLE_MEDIA

Indicates that the storage device supports removable media. Notice that this characteristic indicates removable <i>media</i>, not a removable <i>device</i>. For example, drivers for JAZ drive devices should specify this characteristic, but drivers for PCMCIA flash disks should not.



#### FILE_VIRTUAL_VOLUME

Indicates that the volume is virtual. Drivers should not set this characteristic.



#### FILE_WRITE_ONCE_MEDIA

Indicates that the device supports write-once media. Drivers do not set this member directly. For more information about how to set device characteristics, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563818">Specifying Device Characteristics</a> topic.



#### FILE_CHARACTERISTIC_CSV

Indicates that the device is a Cluster Shared Volume (CSV).



#### FILE_DEVICE_ALLOW_APPCONTAINER_TRAVERSAL

The IO Manager normally performs a full security check for traverse access on every file open when the client is an app container.  Setting of this flag bypasses this enforced traverse access check if the client token already has traverse privileges.



#### FILE_PORTABLE_DEVICE

Indicates that the underlying stack considers the device portable. This is used by the storage stack and means that the device is not in the local machine container and is not on a fixed bus type.


### -field Vpb

A pointer to the volume parameter block (VPB) that is associated with the device object. For file system drivers, the VPB can provide a connection to any unnamed logical device object that represents an instance of a mounted volume. This is an opaque member.


### -field DeviceExtension

A pointer to the device extension. The structure and contents of the device extension are driver-defined. The size is driver-determined, specified in the driver's call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548407">IoCreateDeviceSecure</a>. For more information about device extensions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>. This is a read-only member. However, the object that the member points to can be modified by the driver.


### -field DeviceType

Set by <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff548407">IoCreateDeviceSecure</a> by using the value that is specified for that routine's <i>DeviceType</i> parameter. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a> topic.


### -field StackSize

Specifies the minimum number of stack locations in IRPs to be sent to this driver. <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff548407">IoCreateDeviceSecure</a> set this member to 1 in newly created device objects; lowest-level drivers can therefore ignore this member. The I/O manager automatically sets the <b>StackSize</b> member in a higher-level driver's device object to the appropriate value if the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548294">IoAttachDevice</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548300">IoAttachDeviceToDeviceStack</a>. Only a higher-level driver that chains itself over another driver with <b>IoGetDeviceObjectPointer</b> must explicitly set the value of <b>StackSize</b> in its own device object(s) to 1 + the <b>StackSize</b> value of the next-lower driver's device object.


### -field Queue

Used internally by the I/O manager to queue the device object when it is required. This is an opaque member.


### -field Queue.ListEntry

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that contains forward and backward pointers for a doubly linked list.


### -field Queue.Wcb

Device context information used by I/O manager.


### -field AlignmentRequirement

Specifies the device's address alignment requirement for data transfers. The value must be one of the FILE_<i>XXX</i>_ALIGNMENT values that are defined in Wdm.h. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff546530">GetDmaAlignment</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a> topics.


### -field DeviceQueue

The device queue object for the device object. The device queue object contains any IRPs that are waiting to be processed by the driver that is associated with the device object. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544156">Driver-Managed IRP Queues</a> topic. This is an opaque member.


### -field Dpc

The deferred procedure call (DPC) object for the device object. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548024">Introduction to DPC Objects</a> topic. This is an opaque member.


### -field ActiveThreadCount

Reserved for future use. This is an opaque member.


### -field SecurityDescriptor

Specifies a security descriptor (<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>) for the device object when the device object is created. If this member is <b>NULL</b>, the device object receives default security settings. This is a read-only member, although the member can be modified through the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567106">ZwSetSecurityObject</a>function.


### -field DeviceLock

A synchronization event object that is allocated by the I/O manager. The I/O manager obtains his event object before it dispatches a mount or mount-verify request to a file-system driver. This is an opaque member.


### -field SectorSize

If the device object does not represent a volume, this member is set to zero. If the device object represents a volume, this member specifies the volume's sector size, in bytes. The I/O manager uses this member to make sure that all read operations, write operations, and set file position operations that are issued are aligned correctly when intermediate buffering is disabled. A default system bytes-per-sector value is used when the device object is created, however, file system drivers; and more rarely, legacy and minifilter drivers, can update this value that is based on the geometry of the underlying volume hardware when a mount occurs. Other drivers should not modify this member.


### -field Spare1

Reserved for system use. This is an opaque member.


### -field DeviceObjectExtension

A pointer to a device object extension that is used by the I/O manager and PnP manager to store information about the state of the device. This is an opaque member.


### -field Reserved

Reserved for system use. This is an opaque member.


## -remarks



The operating system represents devices by device objects. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543153">Device Objects and Device Stacks</a> topic.

Drivers create device objects by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff548407">IoCreateDeviceSecure</a> routines. For more information about how to create device objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542862">Creating a Device Object</a>.

A device object is partially opaque. Drivers do not set members of the device object directly, unless otherwise documented. For more information about the members that drivers can modify directly, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a>. For information about other device object properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559925">Properties of Device Objects</a>.

Opaque members within a device object must be considered inaccessible. Drivers that have dependencies on object member locations or access to opaque members might not remain portable and interoperable with other drivers over time.

The system-supplied video port driver sets up the fields of the device objects that it creates on behalf of <a href="https://msdn.microsoft.com/3a540bfe-f340-4f12-acee-323b97683074">video miniport drivers</a>.

The system-supplied SCSI port driver sets up the fields of the device objects that it creates on behalf of <a href="https://msdn.microsoft.com/d9268be8-a68d-4617-b323-349ce7c62f3f">SCSI miniport drivers</a>.

The system-supplied NDIS library sets up the fields of the device objects that it creates on behalf of <a href="https://msdn.microsoft.com/08cd161a-8305-4f3c-94c7-1687cbc34dfd">NDIS miniport drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548294">IoAttachDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548300">IoAttachDeviceToDeviceStack</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549083">IoDeleteDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549198">IoGetDeviceObjectPointer</a>
 

 

