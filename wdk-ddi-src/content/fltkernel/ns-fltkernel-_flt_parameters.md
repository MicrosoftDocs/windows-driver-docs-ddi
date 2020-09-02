---
UID: NS:fltkernel._FLT_PARAMETERS
title: _FLT_PARAMETERS (fltkernel.h)
description: The FLT_PARAMETERS union defines, for a minifilter, the request-type-specific parameters associated with an I/O operation.
old-location: ifsk\flt_parameters.htm
tech.root: ifsk
ms.assetid: 62aa20b7-ce5c-4d42-bce2-1d76a98887ed
ms.date: 11/06/19
keywords: ["FLT_PARAMETERS union"]
ms.keywords: "*PFLT_PARAMETERS, FLT_PARAMETERS, FLT_PARAMETERS union [Installable File System Drivers], FltSystemStructures_2ebb0ec7-76cc-49a3-b2ec-186f67369bbb.xml, PFLT_PARAMETERS, PFLT_PARAMETERS union pointer [Installable File System Drivers], _FLT_PARAMETERS, fltkernel/FLT_PARAMETERS, fltkernel/PFLT_PARAMETERS, ifsk.flt_parameters"
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
targetos: Windows
req.typenames: FLT_PARAMETERS, *PFLT_PARAMETERS
f1_keywords:
 - _FLT_PARAMETERS
 - fltkernel/_FLT_PARAMETERS
 - PFLT_PARAMETERS
 - fltkernel/PFLT_PARAMETERS
 - FLT_PARAMETERS
 - fltkernel/FLT_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FLT_PARAMETERS
---

# _FLT_PARAMETERS union


## -description

The FLT_PARAMETERS union defines, for a minifilter, the request-type-specific parameters associated with an I/O operation. The **Members** section on this reference page lists the members without providing descriptions. Jump directly to [**Remarks**](#remarks) for pointers to the actual structure descriptions.

## -struct-fields

## -remarks

The FLT_PARAMETERS structure is stored in the **Parameters** field of the [FLT_IO_PARAMETER_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_io_parameter_block) structure for the operation. (A pointer to the FLT_IO_PARAMETER_BLOCK structure is stored in the **Iopb** field of the [FLT_CALLBACK_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data) structure for the operation.)

The following table lists each structure member of the FLT_PARAMETERS union and then links to the page that describes that structure's members for the associated IRP. The structures are listed in the order they are defined within FLT_PARAMETERS.

| Structure Name | Description |
| -------------- | ----------- |
| *Create* | [FLT_PARAMETERS for IRP_MJ_CREATE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-create) |
| *CreatePipe* | [FLT_PARAMETERS for IRP_MJ_CREATE_NAMED_PIPE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-create-named-pipe) |
| *CreateMailslot*  | [FLT_PARAMETERS for IRP_MJ_CREATE_MAILSLOT](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-create-mailslot) |
| *Read* | [FLT_PARAMETERS for IRP_MJ_READ](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-read) |
| *Write* | [FLT_PARAMETERS for IRP_MJ_WRITE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-write) |
| *QueryFileInformation* | [FLT_PARAMETERS for IRP_MJ_QUERY_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-information) |
| *SetFileInformation* | [FLT_PARAMETERS for IRP_MJ_SET_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-information) |
| *QueryEa* | [FLT_PARAMETERS for IRP_MJ_QUERY_EA](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-ea) |
| *SetEa* | [FLT_PARAMETERS for IRP_MJ_SET_EA](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-ea) |
| *QueryVolumeInformation* | [FLT_PARAMETERS for IRP_MJ_QUERY_VOLUME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-volume-information) |
| *SetVolumeInformation* | [FLT_PARAMETERS for IRP_MJ_SET_VOLUME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-volume-information) |
| *DirectoryControl* | [FLT_PARAMETERS for IRP_MJ_DIRECTORY_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-directory-control) |
| *FileSystemControl* | [FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-file-system-control) |
| *DeviceIoControl* | [FLT_PARAMETERS for IRP_MJ_DEVICE_CONTROL and IRP_MJ_INTERNAL_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-device-control-and-irp-mj-internal-device-co) |
| *LockControl* | [FLT_PARAMETERS for IRP_MJ_LOCK_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-lock-control) |
| *QuerySecurity* | [FLT_PARAMETERS for IRP_MJ_QUERY_SECURITY](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-security) |
| *SetSecurity* | [FLT_PARAMETERS for IRP_MJ_SET_SECURITY](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-security) |
| *QueryQuota* | [FLT_PARAMETERS for IRP_MJ_QUERY_QUOTA](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-quota) |
| *SetQuota* | [FLT_PARAMETERS for IRP_MJ_SET_QUOTA](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-quota) |
| *Pnp* | [FLT_PARAMETERS for IRP_MJ_PNP](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-pnp) |
| *AcquireForSectionSynchronization* | [FLT_PARAMETERS for IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-acquire-for-section-synchronization) |
| *AcquireForModifiedPageWriter* | [FLT_PARAMETERS for IRP_MJ_ACQUIRE_FOR_MOD_WRITE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-acquire-for-mod-write) |
| *ReleaseForModifiedPageWriter* | [FLT_PARAMETERS for IRP_MJ_RELEASE_FOR_MOD_WRITE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-release-for-mod-write) |
| *QueryOpen* | [FLT_PARAMETERS for IRP_MJ_QUERY_OPEN](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-open) |
| *FastIoCheckIfPossible* | [FLT_PARAMETERS for IRP_MJ_FAST_IO_CHECK_IF_POSSIBLE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-fast-io-check-if-possible) |
| *NetworkQueryOpen* | [FLT_PARAMETERS for IRP_MJ_NETWORK_QUERY_OPEN](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-network-query-open) |
| *MdlRead* | [FLT_PARAMETERS for IRP_MJ_MDL_READ](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-mdl-read) |
| *MdlReadComplete* | [FLT_PARAMETERS for IRP_MJ_MDL_READ_COMPLETE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-mdl-read-complete) |
| *PrepareMdlWrite* | [FLT_PARAMETERS for IRP_MJ_PREPARE_MDL_WRITE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-prepare-mdl-write) |
| *MdlWriteComplete* | [FLT_PARAMETERS for IRP_MJ_MDL_WRITE_COMPLETE](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-mdl-write-complete) |
| *MountVolume* | [FLT_PARAMETERS for IRP_MJ_VOLUME_MOUNT](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-volume-mount) |

The following I/O operations do not have parameters, and therefore do not have a corresponding member within the FLT_PARAMETERS structure. Minifilter drivers that register a callback routine for these I/O operations should perform any needed processing and return:

- IRP_MJ_ACQUIRE_FOR_CC_FLUSH
- IRP_MJ_CLEANUP
- IRP_MJ_CLOSE
- IRP_MJ_FLUSH_BUFFERS
- IRP_MJ_RELEASE_FOR_CC_FLUSH
- IRP_MJ_RELEASE_FOR_SECTION_SYNCHRONIZATION
- IRP_MJ_SHUTDOWN
- IRP_MJ_VOLUME_DISMOUNT

## -see-also

[FLT_CALLBACK_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data)

[FLT_IO_PARAMETER_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_io_parameter_block)

[**FltSetCallbackDataDirty**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetcallbackdatadirty)

