---
UID: NS:wdm._IO_STACK_LOCATION
title: _IO_STACK_LOCATION (wdm.h)
description: The IO_STACK_LOCATION structure defines an I/O stack location, which is an entry in the I/O stack that is associated with each IRP.
old-location: kernel\io_stack_location.htm
tech.root: kernel
ms.assetid: b339d6aa-71e1-4835-8ef2-a84594166bb1
ms.date: 04/30/2018
ms.keywords: "*PIO_STACK_LOCATION, IO_STACK_LOCATION, IO_STACK_LOCATION structure [Kernel-Mode Driver Architecture], PIO_STACK_LOCATION, PIO_STACK_LOCATION structure pointer [Kernel-Mode Driver Architecture], _IO_STACK_LOCATION, kernel.io_stack_location, kstruct_b_8fcba8ca-d004-4800-87d1-d5c7714a494b.xml, wdm/IO_STACK_LOCATION, wdm/PIO_STACK_LOCATION"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- IO_STACK_LOCATION
product:
- Windows
targetos: Windows
req.typenames: IO_STACK_LOCATION, *PIO_STACK_LOCATION
---

# _IO_STACK_LOCATION structure


## -description


The <b>IO_STACK_LOCATION</b> structure defines an <a href="https://msdn.microsoft.com/62c8ee00-c7cb-4aa1-90ab-b8bedbd818ee">I/O stack location</a>, which is an entry in the I/O stack that is associated with each IRP. Each I/O stack location in an IRP has some common members and some request-type-specific members.


## -struct-fields




### -field MajorFunction

The <a href="https://msdn.microsoft.com/11c5b1a9-74c0-47fb-8cce-a008ece9efae">IRP major function code</a> indicating the type of I/O operation to be performed.


### -field MinorFunction

A subfunction code for <b>MajorFunction</b>. The PnP manager, the power manager, file system drivers, and SCSI class drivers set this member for some requests.


### -field Flags

Request-type-specific values used almost exclusively by file system drivers. Removable-media device drivers check whether this member is set with SL_OVERRIDE_VERIFY_VOLUME for read requests to determine whether to continue the read operation even if the device object's <b>Flags</b> is set with DO_VERIFY_VOLUME. Intermediate drivers layered over a removable-media device driver must copy this member into the I/O stack location of the next-lower driver in all incoming <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> requests.

Possible flag values include:

<table>
<tr>
<th>Flag</th>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>SL_KEY_SPECIFIED</td>
<td><code>0x01</code></td>
<td>Indicates that the <code>IO_STACK_LOCATION.Parameters.Read(OrWrite).Key</code>
contains which copy of a given sector should be read when redundancy is enabled.  Today this flag is
use only with IRP_MJ_READ operations.</td>
</tr>
<tr>
<td>SL_OVERRIDE_VERIFY_VOLUME</td>
<td><code>0x02</code></td>
<td>This flag is used to determine whether to continue the read operation even if the device object's <b>Flags</b> is set with DO_VERIFY_VOLUME. </td>
</tr>
<tr>
<td>SL_WRITE_THROUGH</td>
<td><code>0x04</code></td>
<td>This flag informs the storage driver to set appropriate flags so that the disk bypasses the write cache in order to force the disk to write through to its persistent storage media.
<b>This flag is device-specific; not all disk drives support bypassing disk-cache.</b></td>
</tr>
<tr>
<td>SL_FT_SEQUENTIAL_WRITE</td>
<td><code>0x08</code></td>
<td>Reserved for system use.</td>
</tr>
<tr>
<td>SL_FORCE_DIRECT_WRITE</td>
<td><code>0x10</code></td>
<td>
This flag lets kernel-mode drivers write to volume areas that they normally cannot write to because of blocking direct write in the file system and storage driver stack. <b>This flag was introduced in Windows Vista.
</b>


<div class="alert"><b>Note</b>  Direct write blocking, introduced in Windows Vista helps improve security. This flag is checked both at the file system layer and storage stack layer. For more information about direct write blocking, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551353">Blocking Direct Write Operations to Volumes and Disks</a>.</div>
<div> </div>


</td>
</tr>
<tr>
<td>SL_REALTIME_STREAM</td>
<td><code>0x20</code></td>
<td>This flag hints that the IO is for real-time streaming requests to a CD-ROM class driver.
This hints the driver to perform READ/WRITE operations at a guaranteed speed for real-time streaming. <b>This flag is valid only with optical media.</b></td>
</tr>
<tr>
<td>SL_PERSISTENT_MEMORY_FIXED_MAPPING</td>
<td><code>0x20</code></td>
<td>The persistent memory mapping of the bytes in the write request
 cannot change while handling this write request. <b>This flag is valid only with a persistent memory device and IRP_MJ_WRITE.</b></td>
</tr>
</table>
 


<div class="alert"><b>Note</b>  (For persistent memory devices) One of the reasons for remapping (modifying the physical address of a given LBA) on persistent memory
devices is to provide efficient sector level atomicity.
If the flag is not set, remapping is allowed especially if it results in the driver providing sector atomicity.  File systems (or the requester) prefer that a persistent memory device driver provides
sector atomicity.
If the flag is set, a persistent memory driver shall not remap the physical addresses corresponding
to the LBAs.  If that means sector atomicity can't be provided, so be it.  However, the driver is more
than welcome to provide sector atomicity as long as there is no remapping.</div>
<div> </div>



### -field Control

Drivers can check this member to determine whether it is set with SL_PENDING_RETURNED. Drivers have read-only access to this member.


### -field Parameters

A union that depends on the major and minor IRP function code values contained in <b>MajorFunction</b> and <b>MinorFunction</b>. The following table shows which IRPs use the individual members of the <b>Parameters</b> union.

<table>
<tr>
<th>Member name</th>
<th>IRPs that use this member</th>
</tr>
<tr>
<td><b>Create</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>
</td>
</tr>
<tr>
<td><b>Read</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>
</td>
</tr>
<tr>
<td><b>Write</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>
</td>
</tr>
<tr>
<td><b>QueryFile</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549283">IRP_MJ_QUERY_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>SetFile</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>QueryVolume</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>
</td>
</tr>
<tr>
<td><b>DeviceIoControl</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>
</td>
</tr>
<tr>
<td><b>MountVolume</b></td>
<td><b>IRP_MN_MOUNT_VOLUME</b></td>
</tr>
<tr>
<td><b>VerifyVolume</b></td>
<td><b>IRP_MN_VERIFY_VOLUME</b></td>
</tr>
<tr>
<td><b>Scsi</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> (SCSI)</td>
</tr>
<tr>
<td><b>QueryDeviceRelations</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a>
</td>
</tr>
<tr>
<td><b>QueryInterface</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>
</td>
</tr>
<tr>
<td><b>DeviceCapabilities</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a>
</td>
</tr>
<tr>
<td><b>FilterResourceRequirements</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550874">IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>
</td>
</tr>
<tr>
<td><b>ReadWriteConfig</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff551769">IRP_MN_WRITE_CONFIG</a>
</td>
</tr>
<tr>
<td><b>SetLock</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551742">IRP_MN_SET_LOCK</a>
</td>
</tr>
<tr>
<td><b>QueryId</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551679">IRP_MN_QUERY_ID</a>
</td>
</tr>
<tr>
<td><b>QueryDeviceText</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551674">IRP_MN_QUERY_DEVICE_TEXT</a>
</td>
</tr>
<tr>
<td><b>UsageNotification</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550841">IRP_MN_DEVICE_USAGE_NOTIFICATION</a>
</td>
</tr>
<tr>
<td><b>WaitWake</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551766">IRP_MN_WAIT_WAKE</a>
</td>
</tr>
<tr>
<td><b>PowerSequence</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551644">IRP_MN_POWER_SEQUENCE</a>
</td>
</tr>
<tr>
<td><b>Power</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>
</td>
</tr>
<tr>
<td><b>StartDevice</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>
</td>
</tr>
<tr>
<td><b>WMI</b></td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566361">WMI minor IRPs</a>
</td>
</tr>
<tr>
<td><b>Others</b></td>
<td>Driver-specific IRPs</td>
</tr>
</table>
 

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550710">IRP Major Function Codes</a>.


### -field Parameters.Create
System service parameters for **NtCreateFile**.

### -field Parameters.Create.SecurityContext

 


### -field Parameters.Create.Options

 


### -field Parameters.Create.FileAttributes

 


### -field Parameters.Create.ShareAccess

 


### -field Parameters.Create.EaLength

 


### -field Parameters.CreatePipe
 System service parameters fo **NtCreateNamedPipeFile**.

### -field Parameters.CreatePipe.SecurityContext

 


### -field Parameters.CreatePipe.Options

 


### -field Parameters.CreatePipe.Reserved

 


### -field Parameters.CreatePipe.ShareAccess

 


### -field Parameters.CreatePipe.Parameters

 


### -field Parameters.CreateMailslot

System service parameters for  **NtCreateMailslotFile**

### -field Parameters.CreateMailslot.SecurityContext

 


### -field Parameters.CreateMailslot.Options

 


### -field Parameters.CreateMailslot.Reserved

 


### -field Parameters.CreateMailslot.ShareAccess

 


### -field Parameters.CreateMailslot.Parameters

 


### -field Parameters.Read
 System service parameters for **NtReadFile**.

### -field Parameters.Read.Length

 


### -field Parameters.Read.Key

 
### -field Parameters.Read.Flags


### -field Parameters.Read.ByteOffset

 


### -field Parameters.Write
System service parameters for **NtWriteFile**.

### -field Parameters.Write.Length

 


### -field Parameters.Write.Key


### -field Parameters.Write.Flags 


### -field Parameters.Write.ByteOffset

 


### -field Parameters.QueryDirectory
System service parameters for **NtQueryDirectoryFile**.

### -field Parameters.QueryDirectory.Length

 


### -field Parameters.QueryDirectory.FileName

 


### -field Parameters.QueryDirectory.FileInformationClass

 


### -field Parameters.QueryDirectory.FileIndex

 


### -field Parameters.NotifyDirectory
System service parameters for **NtNotifyChangeDirectoryFile**.


### -field Parameters.NotifyDirectory.Length

 


### -field Parameters.NotifyDirectory.CompletionFilter

 


### -field Parameters.NotifyDirectoryEx
System service parameters for **NtNotifyChangeDirectoryFileEx**.

 


### -field Parameters.NotifyDirectoryEx.Length

 


### -field Parameters.NotifyDirectoryEx.CompletionFilter

 


### -field Parameters.NotifyDirectoryEx.DirectoryNotifyInformationClass

 


### -field Parameters.QueryFile
System service parameters for **NtQueryInformationFile**.

### -field Parameters.QueryFile.Length

 


### -field Parameters.QueryFile.FileInformationClass

 


### -field Parameters.SetFile
System service parameters for **NtSetInformationFile**.

### -field Parameters.SetFile.Length

 


### -field Parameters.SetFile.FileInformationClass

 


### -field Parameters.SetFile.FileObject

 


### -field Parameters.SetFile.ReplaceIfExists


### -field Parameters.SetFile.AdvanceOnly


### -field Parameters.SetFile.ClusterCount


### -field Parameters.SetFile.DeleteHandle


### -field Parameters.QueryEa
System service parameters for **NtQueryEaFile**.

### -field Parameters.QueryEa.Length

 


### -field Parameters.QueryEa.EaList

 


### -field Parameters.QueryEa.EaListLength

 


### -field Parameters.QueryEa.EaIndex

 


### -field Parameters.SetEa
System service parameters for **NtSetEaFile**.

### -field Parameters.SetEa.Length

 


### -field Parameters.QueryVolume
System service parameters for **NtQueryVolumeInformationFile**.

### -field Parameters.QueryVolume.Length

 


### -field Parameters.QueryVolume.FsInformationClass

 


### -field Parameters.SetVolume
System service parameters for **NtSetVolumeInformationFile**.


### -field Parameters.SetVolume.Length

 


### -field Parameters.SetVolume.FsInformationClass

 


### -field Parameters.FileSystemControl
System service parameters for **NtFsControlFile**.


### -field Parameters.FileSystemControl.OutputBufferLength

 


### -field Parameters.FileSystemControl.InputBufferLength

 


### -field Parameters.FileSystemControl.FsControlCode

 


### -field Parameters.FileSystemControl.Type3InputBuffer

 


### -field Parameters.LockControl
System service parameters for **LockFile/NtUnlockFile**.

### -field Parameters.LockControl.Length

 


### -field Parameters.LockControl.Key

 


### -field Parameters.LockControl.ByteOffset

 


### -field Parameters.DeviceIoControl
System service parameters for **NtDeviceIoControlFile**.

### -field Parameters.DeviceIoControl.OutputBufferLength

 


### -field Parameters.DeviceIoControl.InputBufferLength

 


### -field Parameters.DeviceIoControl.IoControlCode

 


### -field Parameters.DeviceIoControl.Type3InputBuffer

 


### -field Parameters.QuerySecurity
System service parameters for **NtQuerySecurityObject**.


### -field Parameters.QuerySecurity.SecurityInformation

 


### -field Parameters.QuerySecurity.Length

 


### -field Parameters.SetSecurity
System service parameters for **NtSetSecurityObject**.

### -field Parameters.SetSecurity.SecurityInformation

 


### -field Parameters.SetSecurity.SecurityDescriptor

 


### -field Parameters.MountVolume
System service parameters for **MountVolume**.


### -field Parameters.MountVolume.Vpb

 


### -field Parameters.MountVolume.DeviceObject

 


### -field Parameters.VerifyVolume
System service parameters for **VerifyVolume**.


### -field Parameters.VerifyVolume.Vpb

 


### -field Parameters.VerifyVolume.DeviceObject

 


### -field Parameters.Scsi
Parameters for Scsi with internal device control.


### -field Parameters.Scsi.Srb

 


### -field Parameters.QueryQuota
System service parameters for **NtSetQuotaInformationFile**.

### -field Parameters.QueryQuota.Length

 


### -field Parameters.QueryQuota.StartSid

 


### -field Parameters.QueryQuota.SidList

 


### -field Parameters.QueryQuota.SidListLength

 


### -field Parameters.SetQuota
System service parameters for **NtSetQuotaInformationFile**.

### -field Parameters.SetQuota.Length

 


### -field Parameters.QueryDeviceRelations
Parameters for IRP_MN_QUERY_DEVICE_RELATIONS.

### -field Parameters.QueryDeviceRelations.Type

 


### -field Parameters.QueryInterface
Parameters for IRP_MN_QUERY_INTERFACE.

### -field Parameters.QueryInterface.InterfaceType

 


### -field Parameters.QueryInterface.Size

 


### -field Parameters.QueryInterface.Version

 


### -field Parameters.QueryInterface.Interface

 


### -field Parameters.QueryInterface.InterfaceSpecificData

 


### -field Parameters.DeviceCapabilities
Parameters for IRP_MN_QUERY_CAPABILITIES.

### -field Parameters.DeviceCapabilities.Capabilities

 


### -field Parameters.FilterResourceRequirements
Parameters for IRP_MN_FILTER_RESOURCE_REQUIREMENTS.

### -field Parameters.FilterResourceRequirements.IoResourceRequirementList

 


### -field Parameters.ReadWriteConfig
Parameters for IRP_MN_READ_CONFIG and IRP_MN_WRITE_CONFIG.

### -field Parameters.ReadWriteConfig.WhichSpace

 


### -field Parameters.ReadWriteConfig.Buffer

 


### -field Parameters.ReadWriteConfig.Offset

 


### -field Parameters.ReadWriteConfig.Length

 


### -field Parameters.SetLock
Parameters for IRP_MN_SET_LOCK.

### -field Parameters.SetLock.Lock

 


### -field Parameters.QueryId
Parameters for IRP_MN_QUERY_ID.

### -field Parameters.QueryId.IdType

 


### -field Parameters.QueryDeviceText
Parameters for IRP_MN_QUERY_DEVICE_TEXT.

### -field Parameters.QueryDeviceText.DeviceTextType

 


### -field Parameters.QueryDeviceText.LocaleId

 


### -field Parameters.UsageNotification
Parameters for IRP_MN_DEVICE_USAGE_NOTIFICATION.

### -field Parameters.UsageNotification.InPath

 


### -field Parameters.UsageNotification.Reserved

 


### -field Parameters.UsageNotification.Type

 


### -field Parameters.WaitWake
Parameters for IRP_MN_WAIT_WAKE.

### -field Parameters.WaitWake.PowerState

 


### -field Parameters.PowerSequence
Parameter for IRP_MN_POWER_SEQUENCE.

### -field Parameters.PowerSequence.PowerSequence

 


### -field Parameters.Power.SystemPowerStateContext


### -field Parameters.Power
Parameters for IRP_MN_SET_POWER and IRP_MN_QUERY_POWER.

### -field Parameters.Power.SystemContext


### -field Parameters.Power.Type

 


### -field Parameters.Power.State

 


### -field Parameters.Power.ShutdownType

 


### -field Parameters.StartDevice
 Parameters for StartDevice.

### -field Parameters.StartDevice.AllocatedResources

 


### -field Parameters.StartDevice.AllocatedResourcesTranslated

 


### -field Parameters.WMI
 Parameters for WMI IRPs.

### -field Parameters.WMI.ProviderId

 


### -field Parameters.WMI.DataPath

 


### -field Parameters.WMI.BufferSize

 


### -field Parameters.WMI.Buffer

 


### -field Parameters.Others
Parameters for other driver-specific operations.

### -field Parameters.Others.Argument1

 


### -field Parameters.Others.Argument2

 


### -field Parameters.Others.Argument3

 


### -field Parameters.Others.Argument4

 


### -field DeviceObject

A pointer to the driver-created <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure representing the target physical, logical, or virtual device for which this driver is to handle the IRP.


### -field FileObject

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> structure that represents the file object, if any, that is associated with <b>DeviceObject</b> pointer. 


### -field CompletionRoutine
The completion routines that is invoked depending on the flags in the preceding flags field.

### -field Context
Driver-defined context that is used to store the address of the context parameter that is passed to the CompletionRoutine.

## -remarks



For each IRP, there is one <b>IO_STACK_LOCATION</b> structure for each driver in a <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">driver stack</a>. Each IRP's set of I/O stack locations is appended to the IRP, following the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure.

Every higher-level driver is responsible for setting up the I/O stack location for the next-lower driver in each IRP. A driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549174">IoGetCurrentIrpStackLocation</a> to get a pointer to its own stack location for each IRP. Higher-level drivers can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549266">IoGetNextIrpStackLocation</a> to get a pointer to the next-lower driver's stack location.

The higher-level driver must set up the stack location contents before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a> to pass an IRP to the lower-level driver. If the driver will pass the input IRP on to the next lower-level driver, the dispatch routine should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548387">IoCopyCurrentIrpStackLocationToNext</a> to set up the I/O stack location of the next-lower driver.

A higher-level driver's call to <b>IoCallDriver</b> sets the <b>DeviceObject</b> member to the next-lower-level driver's target device object, in the I/O stack location of the lower driver. The I/O manager passes each higher-level driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine a pointer to its own device object when the <i>IoCompletion</i> routine is called on completion of the IRP.

If a higher-level driver allocates IRPs to make requests of its own, its <i>IoCompletion</i> routine is passed a <b>NULL</b> <b>DeviceObject</b> pointer if that driver neither allocates a stack location for itself nor sets up the <b>DeviceObject</b> pointer in its own stack location of the newly allocated IRP.

In some cases, a higher-level driver layered over a mass-storage device driver is responsible for splitting up large transfer requests for the underlying device driver. In particular, SCSI class drivers must check the <b>Parameters.Read.Length</b> and <b>Parameters.Write.Length</b>, determine whether the size of the requested transfer exceeds the underlying HBA's transfer capabilities, and, if so, split the <b>Length</b> of the original request into a sequence of partial transfers to satisfy the original IRP.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548387">IoCopyCurrentIrpStackLocationToNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549174">IoGetCurrentIrpStackLocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549266">IoGetNextIrpStackLocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550321">IoSetNextIrpStackLocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>
 

 

