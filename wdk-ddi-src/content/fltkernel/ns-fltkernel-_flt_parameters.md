---
UID: NS:fltkernel._FLT_PARAMETERS
title: _FLT_PARAMETERS (fltkernel.h)
description: The FLT_PARAMETERS union defines the request-type-specific parameters associated with an I/O operation.
old-location: ifsk\flt_parameters.htm
tech.root: ifsk
ms.assetid: 62aa20b7-ce5c-4d42-bce2-1d76a98887ed
ms.date: 10/30/2019
ms.keywords: "*PFLT_PARAMETERS, FLT_PARAMETERS, FLT_PARAMETERS union [Installable File System Drivers], FltSystemStructures_2ebb0ec7-76cc-49a3-b2ec-186f67369bbb.xml, PFLT_PARAMETERS, PFLT_PARAMETERS union pointer [Installable File System Drivers], _FLT_PARAMETERS, fltkernel/FLT_PARAMETERS, fltkernel/PFLT_PARAMETERS, ifsk.flt_parameters"
ms.topic: struct
f1_keywords:
 - "fltkernel/FLT_PARAMETERS"
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
- fltkernel.h
api_name:
- FLT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: FLT_PARAMETERS, *PFLT_PARAMETERS
---

# _FLT_PARAMETERS union

## -description

The FLT_PARAMETERS union defines the request-type-specific parameters associated with an I/O operation. The long **Members** section on this reference page simply lists the members without providing descriptions. Instead, jump to the [**Remarks**](#remarks) section for pointers to the actual structure descriptions.

## -struct-fields

## -remarks

The FLT_PARAMETERS structure is stored in the **Parameters** field of the [FLT_IO_PARAMETER_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_io_parameter_block) structure for the operation. (A pointer to the FLT_IO_PARAMETER_BLOCK structure is stored in the **Iopb** field of the [FLT_CALLBACK_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data) structure for the operation.)

The following table identifies the IRP associated with each structure of the FLT_PARAMETERS union, and provides a link to the page that describes that structure's members. The structures are listed in the order that they are defined within FLT_PARAMETERS.

| Structure Name | Associated IRP | Associated Reference Page |
| -------------- | -------------- | ------------------------- |
| *Create* | [IRP_MJ_CREATE](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create) | [FLT_PARAMETERS for IRP_MJ_CREATE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-create) |
| *CreatePipe* | IRP_MJ_CREATE_NAMED_PIPE | [FLT_PARAMETERS for IRP_MJ_CREATE_NAMED_PIPE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-create-pipe) |
| *CreateMailslot* | IRP_MJ_CREATE_MAILSLOT | [FLT_PARAMETERS for IRP_MJ_CREATE_MAILSLOT](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-create-mailslot) |
| *Read* | [IRP_MJ_READ](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-read) | [FLT_PARAMETERS for IRP_MJ_READ](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-read) |
| *Write* | [IRP_MJ_WRITE](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-write) | [FLT_PARAMETERS for IRP_MJ_WRITE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-write) |
| *QueryFileInformation* | [IRP_MJ_QUERY_INFORMATION](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-query-information) | [FLT_PARAMETERS for IRP_MJ_QUERY_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-information) |
| *SetFileInformation* | [IRP_MJ_SET_INFORMATION](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-set-information) | [FLT_PARAMETERS for IRP_MJ_SET_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-information) |
| *QueryEa* | [IRP_MJ_QUERY_EA](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-query-ea) | [FLT_PARAMETERS for IRP_MJ_QUERY_EA](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-ea) |
| *SetEa* | [IRP_MJ_SET_EA](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-set-ea) | [FLT_PARAMETERS for IRP_MJ_SET_EA](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-ea) |
| *QueryVolumeInformation* | [IRP_MJ_QUERY_VOLUME_INFORMATION](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-query-volume-information) | [FLT_PARAMETERS for IRP_MJ_QUERY_VOLUME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-volume-information) |
| *SetVolumeInformation* | [IRP_MJ_SET_VOLUME_INFORMATION](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-set-volume-information) | [FLT_PARAMETERS for IRP_MJ_SET_VOLUME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-volume-information) |
| *DirectoryControl* | [IRP_MJ_DIRECTORY_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-directory-control) | [FLT_PARAMETERS for IRP_MJ_DIRECTORY_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-directory-control) |
| *FileSystemControl* | [IRP_MJ_FILE_SYSTEM_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-file-system-control) | [FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-file-system-control) |
| *DeviceIoControl* | [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-device-control), [IRP_MJ_INTERNAL_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-internal-device-control) | [FLT_PARAMETERS for IRP_MJ_DEVICE_CONTROL and IRP_MJ_INTERNAL_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-device-control-and-irp-mj-internal-device-co) |
| *LockControl* | [IRP_MJ_LOCK_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-lock-control) | [FLT_PARAMETERS for IRP_MJ_LOCK_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-lock-control) |
| *QuerySecurity* | [IRP_MJ_QUERY_SECURITY](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-query-security) | [FLT_PARAMETERS for IRP_MJ_QUERY_SECURITY](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-security) |
| *SetSecurity* | [IRP_MJ_SET_SECURITY](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-set-security) | [FLT_PARAMETERS for IRP_MJ_SET_SECURITY](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-security) |
| *QueryQuota* | [IRP_MJ_QUERY_QUOTA](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-query-quota) | [FLT_PARAMETERS for IRP_MJ_QUERY_QUOTA](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-quota) |
| *SetQuota* | [IRP_MJ_SET_QUOTA](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-set-quota) | [FLT_PARAMETERS for IRP_MJ_SET_QUOTA](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-quota) |
| *Pnp* | [IRP_MJ_PNP](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-pnp) | [FLT_PARAMETERS for IRP_MJ_PNP](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-pnp) |
| *AcquireForSectionSynchronization* | IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION | [FLT_PARAMETERS for IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-acquire-for-section-synchronization) |
| *AcquireForModifiedPageWriter* | IRP_MJ_ACQUIRE_FOR_MOD_WRITE | [FLT_PARAMETERS for IRP_MJ_ACQUIRE_FOR_MOD_WRITE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-acquire-for-mod-write) |
| *ReleaseForModifiedPageWriter* | IRP_MJ_RELEASE_FOR_MOD_WRITE | [FLT_PARAMETERS for IRP_MJ_RELEASE_FOR_MOD_WRITE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-release-for-mod-write) |
| *QueryOpen* | IRP_MJ_QUERY_OPEN | [FLT_PARAMETERS for IRP_MJ_QUERY_OPEN](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-open) |
| *FastIoCheckIfPossible* | IRP_MJ_FAST_IO_CHECK_IF_POSSIBLE | [FLT_PARAMETERS for IRP_MJ_FAST_IO_CHECK_IF_POSSIBLE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-fast-io-check-if-possible) |
| *NetworkQueryOpen* | IRP_MJ_NETWORK_QUERY_OPEN | [FLT_PARAMETERS for IRP_MJ_NETWORK_QUERY_OPEN](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-network-query-open) |
| *MdlRead* | IRP_MJ_MDL_READ | [FLT_PARAMETERS for IRP_MJ_MDL_READ](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-mdl-read) |
| *MdlReadComplete* | IRP_MJ_MDL_READ_COMPLETE | [FLT_PARAMETERS for IRP_MJ_MDL_READ_COMPLETE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-mdl-read-complete) |
| *PrepareMdlWrite* | IRP_MJ_PREPARE_MDL_WRITE | [FLT_PARAMETERS for IRP_MJ_PREPARE_MDL_WRITE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-prepare-mdl-write) |
| *MdlWriteComplete* | IRP_MJ_MDL_WRITE_COMPLETE | [FLT_PARAMETERS for IRP_MJ_MDL_WRITE_COMPLETE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-mdl-write-complete) |
| *MountVolume* | IRP_MJ_VOLUME_MOUNT | [FLT_PARAMETERS for IRP_MJ_VOLUME_MOUNT](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-volume-mount) |

The following I/O operations do not have parameters, and therefore do not have a corresponding member within the FLT_PARAMETERS structure:

- IRP_MJ_ACQUIRE_FOR_CC_FLUSH
- [IRP_MJ_CLEANUP](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-cleanup)
- [IRP_MJ_CLOSE](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-close)
- [IRP_MJ_FLUSH_BUFFERS](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-flush-buffers)
- IRP_MJ_RELEASE_FOR_CC_FLUSH
- IRP_MJ_RELEASE_FOR_SECTION_SYNCHRONIZATION
- [IRP_MJ_SHUTDOWN](https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/irp-mj-shutdown)
- IRP_MJ_VOLUME_DISMOUNT

## -see-also

[FLT_CALLBACK_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data)

[FLT_IO_PARAMETER_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_io_parameter_block)

[FltSetCallbackDataDirty](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcallbackdatadirty)
