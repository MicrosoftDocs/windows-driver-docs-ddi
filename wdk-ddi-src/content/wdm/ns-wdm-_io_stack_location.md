---
UID: NS:wdm._IO_STACK_LOCATION
title: IO_STACK_LOCATION (wdm.h)
description: The IO_STACK_LOCATION structure defines an I/O stack location, which is an entry in the I/O stack that is associated with each IRP.
tech.root: kernel
ms.date: 09/20/2023
keywords: ["IO_STACK_LOCATION structure"]
ms.keywords: "*PIO_STACK_LOCATION, IO_STACK_LOCATION, IO_STACK_LOCATION structure [Kernel-Mode Driver Architecture], PIO_STACK_LOCATION, PIO_STACK_LOCATION structure pointer [Kernel-Mode Driver Architecture], _IO_STACK_LOCATION, kernel.io_stack_location, kstruct_b_8fcba8ca-d004-4800-87d1-d5c7714a494b.xml, wdm/IO_STACK_LOCATION, wdm/PIO_STACK_LOCATION"
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
targetos: Windows
req.typenames: IO_STACK_LOCATION, *PIO_STACK_LOCATION
f1_keywords:
 - _IO_STACK_LOCATION
 - wdm/_IO_STACK_LOCATION
 - PIO_STACK_LOCATION
 - wdm/PIO_STACK_LOCATION
 - IO_STACK_LOCATION
 - wdm/IO_STACK_LOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _IO_STACK_LOCATION
 - PIO_STACK_LOCATION
 - IO_STACK_LOCATION
---

## -description

The **IO_STACK_LOCATION** structure defines an [I/O stack location](/windows-hardware/drivers/kernel/i-o-stack-locations), which is an entry in the I/O stack that is associated with each IRP. Each I/O stack location in an IRP has some common members and some request-type-specific members.

## -struct-fields

### -field MajorFunction

The [IRP major function code](/windows-hardware/drivers/kernel/irp-major-function-codes) indicating the type of I/O operation to be performed.

### -field MinorFunction

A subfunction code for **MajorFunction**. The PnP manager, the power manager, file system drivers, and SCSI class drivers set this member for some requests.

### -field Flags

Request-type-specific values used almost exclusively by file system drivers. Removable-media device drivers check whether this member is set with SL_OVERRIDE_VERIFY_VOLUME for read requests to determine whether to continue the read operation even if the device object's **Flags** is set with DO_VERIFY_VOLUME. Intermediate drivers layered over a removable-media device driver must copy this member into the I/O stack location of the next-lower driver in all incoming [IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read) requests.

For documentation of other `SL_*` flags for IRP_MJ_CREATE, see [IRP_MJ_CREATE (IFS)](/windows-hardware/drivers/ifs/irp-mj-create).

Possible flag values include:

| Flag | Value | Description |
|---|---|---|
| SL_KEY_SPECIFIED | `0x01` | Indicates that the `IO_STACK_LOCATION.Parameters.Read(OrWrite).Key` contains which copy of a given sector should be read when redundancy is enabled. Today this flag is use only with IRP_MJ_READ operations. |
| SL_OVERRIDE_VERIFY_VOLUME | `0x02` | This flag is used to determine whether to continue the read operation even if the device object's **Flags** is set with DO_VERIFY_VOLUME. |
| SL_WRITE_THROUGH | `0x04` | This flag informs the storage driver to set appropriate flags so that the disk bypasses the write cache in order to force the disk to write through to its persistent storage media. **This flag is device-specific; not all disk drives support bypassing disk-cache.** |
| SL_FT_SEQUENTIAL_WRITE | `0x08` | Reserved for system use. |
| SL_FORCE_DIRECT_WRITE | `0x10` | This flag lets kernel-mode drivers write to volume areas that they normally cannot write to because of blocking direct write in the file system and storage driver stack.  Direct write blocking helps improve security. This flag is checked both at the file system layer and storage stack layer. For more information about direct write blocking, see [Blocking Direct Write Operations to Volumes and Disks](../index.yml). |
| SL_REALTIME_STREAM | `0x20` | This flag hints that the IO is for real-time streaming requests to a CD-ROM class driver. This hints the driver to perform READ/WRITE operations at a guaranteed speed for real-time streaming. **This flag is valid only with optical media.** |
| SL_PERSISTENT_MEMORY_FIXED_MAPPING | `0x20` | The persistent memory mapping of the bytes in the write request cannot change while handling this write request. **This flag is valid only with a persistent memory device and IRP_MJ_WRITE.** |

For persistent memory devices, one of the reasons for remapping (modifying the physical address of a given LBA) on persistent memory devices is to provide efficient sector level atomicity. If the flag is not set, remapping is allowed especially if it results in the driver providing sector atomicity.  File systems (or the requester) prefer that a persistent memory device driver provides sector atomicity.
If the flag is set, a persistent memory driver shall not remap the physical addresses corresponding
to the LBAs.  If that means sector atomicity can't be provided, so be it.  However, the driver is more
than welcome to provide sector atomicity as long as there is no remapping.

### -field Control

Drivers can check this member to determine whether it is set with SL_PENDING_RETURNED and under what conditions the *CompletionRoutine* is called. Drivers have read-only access to this member. Drivers call [**IoSetCompletionRoutine**](nf-wdm-iosetcompletionroutine.md) or [**IoSetCompletionRoutineEx**](nf-wdm-iosetcompletionroutineex.md) to specify these conditions.

### -field Parameters

A union that depends on the major and minor IRP function code values contained in **MajorFunction** and **MinorFunction**. The following table shows which IRPs use the individual members of the **Parameters** union.

| Member name | IRPs that use this member |
|---|---|
| **Create** | [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) |
| **Read** | [IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read) |
| **Write** | [IRP_MJ_WRITE](/windows-hardware/drivers/kernel/irp-mj-write) |
| **QueryFile** | [IRP_MJ_QUERY_INFORMATION](/windows-hardware/drivers/ifs/irp-mj-query-information) |
| **SetFile** | [IRP_MJ_SET_INFORMATION](/windows-hardware/drivers/ifs/irp-mj-set-information) |
| **QueryVolume** | [IRP_MJ_QUERY_VOLUME_INFORMATION](/windows-hardware/drivers/ifs/irp-mj-query-volume-information) |
| **DeviceIoControl** | [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/ifs/irp-mj-device-control) and [IRP_MJ_INTERNAL_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-internal-device-control) |
| **MountVolume** | **IRP_MN_MOUNT_VOLUME** |
| **VerifyVolume** | **IRP_MN_VERIFY_VOLUME** |
| **Scsi** | [IRP_MJ_INTERNAL_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-internal-device-control) (SCSI) |
| **QueryDeviceRelations** | [IRP_MN_QUERY_DEVICE_RELATIONS](/windows-hardware/drivers/kernel/irp-mn-query-device-relations) |
| **QueryInterface** | [IRP_MN_QUERY_INTERFACE](/windows-hardware/drivers/kernel/irp-mn-query-interface) |
| **DeviceCapabilities** | [IRP_MN_QUERY_CAPABILITIES](/windows-hardware/drivers/kernel/irp-mn-query-capabilities) |
| **FilterResourceRequirements** | [IRP_MN_FILTER_RESOURCE_REQUIREMENTS](/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements) |
| **ReadWriteConfig** | [IRP_MN_READ_CONFIG](/windows-hardware/drivers/kernel/irp-mn-read-config) and [IRP_MN_WRITE_CONFIG](/windows-hardware/drivers/kernel/irp-mn-write-config) |
| **SetLock** | [IRP_MN_SET_LOCK](/windows-hardware/drivers/kernel/irp-mn-set-lock) |
| **QueryId** | [IRP_MN_QUERY_ID](/windows-hardware/drivers/kernel/irp-mn-query-id) |
| **QueryDeviceText** | [IRP_MN_QUERY_DEVICE_TEXT](/windows-hardware/drivers/kernel/irp-mn-query-device-text) |
| **UsageNotification** | [IRP_MN_DEVICE_USAGE_NOTIFICATION](/windows-hardware/drivers/kernel/irp-mn-device-usage-notification) |
| **WaitWake** | [IRP_MN_WAIT_WAKE](/windows-hardware/drivers/kernel/irp-mn-wait-wake) |
| **PowerSequence** | [IRP_MN_POWER_SEQUENCE](/windows-hardware/drivers/kernel/irp-mn-power-sequence) |
| **Power** | [IRP_MN_SET_POWER](/windows-hardware/drivers/kernel/irp-mn-set-power) and [IRP_MN_QUERY_POWER](/windows-hardware/drivers/kernel/irp-mn-query-power) |
| **StartDevice** | [IRP_MN_START_DEVICE](/windows-hardware/drivers/kernel/irp-mn-start-device) |
| **WMI** | [WMI minor IRPs](/windows-hardware/drivers/kernel/wmi-minor-irps) |
| **Others** | Driver-specific IRPs |

For more information, see [IRP Major Function Codes](/windows-hardware/drivers/kernel/irp-major-function-codes).

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

System service parameters for  **NtCreateMailslotFile**.

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

System service parameters for [**NtQueryQuotaInformationFile**](../ntifs/nf-ntifs-ntqueryquotainformationfile.md).

### -field Parameters.QueryQuota.Length

### -field Parameters.QueryQuota.StartSid

### -field Parameters.QueryQuota.SidList

### -field Parameters.QueryQuota.SidListLength

### -field Parameters.SetQuota

System service parameters for [**NtSetQuotaInformationFile**](../ntifs/nf-ntifs-ntsetquotainformationfile.md).

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

### -field Parameters.UsageNotification.Reserved[3]

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

A pointer to the driver-created [**DEVICE_OBJECT**](./ns-wdm-_device_object.md) structure representing the target physical, logical, or virtual device for which this driver is to handle the IRP.

### -field FileObject

A pointer to a [**FILE_OBJECT**](./ns-wdm-_file_object.md) structure that represents the file object, if any, that is associated with **DeviceObject** pointer.

### -field CompletionRoutine

The completion routine that is invoked depending on the flags in the **Control** field of this structure.

### -field Context

Driver-defined context that is used to store the address of the context parameter that is passed to the CompletionRoutine.

## -remarks

For each IRP, there is one **IO_STACK_LOCATION** structure for each driver in a [driver stack](/windows-hardware/drivers/). Each IRP's set of I/O stack locations is appended to the IRP, following the [**IRP**](./ns-wdm-_irp.md) structure.

Every higher-level driver is responsible for setting up the I/O stack location for the next-lower driver in each IRP. A driver must call [IoGetCurrentIrpStackLocation](./nf-wdm-iogetcurrentirpstacklocation.md) to get a pointer to its own stack location for each IRP. Higher-level drivers can call [IoGetNextIrpStackLocation](./nf-wdm-iogetnextirpstacklocation.md) to get a pointer to the next-lower driver's stack location.

The higher-level driver must set up the stack location contents before calling [IoCallDriver](./nf-wdm-iocalldriver.md) to pass an IRP to the lower-level driver. If the driver will pass the input IRP on to the next lower-level driver, the dispatch routine should call [IoSkipCurrentIrpStackLocation](./nf-wdm-ioskipcurrentirpstacklocation.md) or [IoCopyCurrentIrpStackLocationToNext](./nf-wdm-iocopycurrentirpstacklocationtonext.md) to set up the I/O stack location of the next-lower driver.

A higher-level driver's call to **IoCallDriver** sets the **DeviceObject** member to the next-lower-level driver's target device object, in the I/O stack location of the lower driver. The I/O manager passes each higher-level driver's [IoCompletion](./nc-wdm-io_completion_routine.md) routine a pointer to its own device object when the *IoCompletion* routine is called on completion of the IRP.

If a higher-level driver allocates IRPs to make requests of its own, its *IoCompletion* routine is passed a **NULL** **DeviceObject** pointer if that driver neither allocates a stack location for itself nor sets up the **DeviceObject** pointer in its own stack location of the newly allocated IRP.

In some cases, a higher-level driver layered over a mass-storage device driver is responsible for splitting up large transfer requests for the underlying device driver. In particular, SCSI class drivers must check the **Parameters.Read.Length** and **Parameters.Write.Length**, determine whether the size of the requested transfer exceeds the underlying HBA's transfer capabilities, and, if so, split the **Length** of the original request into a sequence of partial transfers to satisfy the original IRP.

## -see-also

[**IO_STATUS_BLOCK**](./ns-wdm-_io_status_block.md)

[**IRP**](./ns-wdm-_irp.md)

[IoCallDriver](./nf-wdm-iocalldriver.md)

[IoCopyCurrentIrpStackLocationToNext](./nf-wdm-iocopycurrentirpstacklocationtonext.md)

[IoGetCurrentIrpStackLocation](./nf-wdm-iogetcurrentirpstacklocation.md)

[IoGetNextIrpStackLocation](./nf-wdm-iogetnextirpstacklocation.md)

[IoSetCompletionRoutine](./nf-wdm-iosetcompletionroutine.md)

[IoSetNextIrpStackLocation](./nf-wdm-iosetnextirpstacklocation.md)

[IoSkipCurrentIrpStackLocation](./nf-wdm-ioskipcurrentirpstacklocation.md)