---
UID: NE:wdm._FILE_INFORMATION_CLASS
title: FILE_INFORMATION_CLASS (wdm.h)
description: Learn more about the FILE_INFORMATION_CLASS enumeration.
tech.root: ifsk
ms.date: 02/06/2024
author: lorihollasch
keywords: ["FILE_INFORMATION_CLASS enumeration"]
req.header: wdm.h
req.include-header: FltKernel.h, Ntifs.h
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
req.typenames: FILE_INFORMATION_CLASS, *PFILE_INFORMATION_CLASS
f1_keywords:
 - _FILE_INFORMATION_CLASS
 - wdm/_FILE_INFORMATION_CLASS
 - PFILE_INFORMATION_CLASS
 - wdm/PFILE_INFORMATION_CLASS
 - FILE_INFORMATION_CLASS
 - wdm/FILE_INFORMATION_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
 - wdm.h
api_name:
 - _FILE_INFORMATION_CLASS
 - PFILE_INFORMATION_CLASS
 - FILE_INFORMATION_CLASS
---

## -description

A **FILE_INFORMATION_CLASS** value specifies which structure to use to query or set information for a file object.

## -enum-fields

### -field FileDirectoryInformation:1

A [**FILE_DIRECTORY_INFORMATION**](../ntifs/ns-ntifs-_file_directory_information.md) structure.

### -field FileFullDirectoryInformation:2

A [**FILE_FULL_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_full_dir_information.md) structure.

### -field FileBothDirectoryInformation:3

A [**FILE_BOTH_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_both_dir_information.md) structure.

### -field FileBasicInformation:4

A [**FILE_BASIC_INFORMATION**](ns-wdm-_file_basic_information.md) structure.

### -field FileStandardInformation:5

A [**FILE_STANDARD_INFORMATION**](ns-wdm-_file_standard_information.md) structure.

### -field FileInternalInformation:6

A [**FILE_INTERNAL_INFORMATION**](../ntifs/ns-ntifs-_file_internal_information.md) structure.

### -field FileEaInformation:7

A [**FILE_EA_INFORMATION**](../ntifs/ns-ntifs-_file_ea_information.md) structure.

### -field FileAccessInformation:8

A [**FILE_ACCESS_INFORMATION**](../ntifs/ns-ntifs-_file_access_information.md) structure.

### -field FileNameInformation:9

A [**FILE_NAME_INFORMATION**](../ntddk/ns-ntddk-_file_name_information.md) structure.

### -field FileRenameInformation:10

A [**FILE_RENAME_INFORMATION**](../ntifs/ns-ntifs-_file_rename_information.md) structure.

### -field FileLinkInformation:11

A [**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md) structure.

### -field FileNamesInformation:12

A [**FILE_NAMES_INFORMATION**](../ntifs/ns-ntifs-_file_names_information.md) structure.

### -field FileDispositionInformation:13

A [**FILE_DISPOSITION_INFORMATION**](../ntddk/ns-ntddk-_file_disposition_information.md) structure.

### -field FilePositionInformation:14

A [**FILE_POSITION_INFORMATION**](ns-wdm-_file_position_information.md) structure.

### -field FileFullEaInformation:15

A [**FILE_FULL_EA_INFORMATION**](ns-wdm-_file_full_ea_information.md) structure.

### -field FileModeInformation:16

A [**FILE_MODE_INFORMATION**](../ntifs/ns-ntifs-_file_mode_information.md) structure.

### -field FileAlignmentInformation:17

A [**FILE_ALIGNMENT_INFORMATION**](../ntddk/ns-ntddk-_file_alignment_information.md) structure.

### -field FileAllInformation:18

A [**FILE_ALL_INFORMATION**](../ntifs/ns-ntifs-_file_all_information.md) structure.

### -field FileAllocationInformation:19

A [**FILE_ALLOCATION_INFORMATION**](../ntifs/ns-ntifs-_file_allocation_information.md) structure.

### -field FileEndOfFileInformation:20

A [**FILE_END_OF_FILE_INFORMATION**](../ntddk/ns-ntddk-_file_end_of_file_information.md) structure.

### -field FileAlternateNameInformation:21

A [**FILE_NAME_INFORMATION**](../ntddk/ns-ntddk-_file_name_information.md) structure.

### -field FileStreamInformation:22

A message buffer that contains one or more [**FILE_STREAM_INFORMATION**](../ntifs/ns-ntifs-_file_stream_information.md) structures.

### -field FilePipeInformation:23

A [**FILE_PIPE_INFORMATION**](../ntifs/ns-ntifs-_file_pipe_information.md) structure.

### -field FilePipeLocalInformation:24

A [**FILE_PIPE_LOCAL_INFORMATION**](../ntifs/ns-ntifs-_file_pipe_local_information.md) structure.

### -field FilePipeRemoteInformation:25

A [**FILE_PIPE_REMOTE_INFORMATION**](../ntifs/ns-ntifs-_file_pipe_remote_information.md) structure.

### -field FileMailslotQueryInformation:26

A [**FILE_MAILSLOT_QUERY_INFORMATION**](../ntifs/ns-ntifs-_file_mailslot_query_information.md) structure.

### -field FileMailslotSetInformation:27

A [**FILE_MAILSLOT_SET_INFORMATION**](../ntifs/ns-ntifs-_file_mailslot_set_information.md) structure.

### -field FileCompressionInformation:28

A [**FILE_COMPRESSION_INFORMATION**](../ntifs/ns-ntifs-_file_compression_information.md) structure.

### -field FileObjectIdInformation:29

A [**FILE_OBJECTID_INFORMATION**](../ntifs/ns-ntifs-_file_objectid_information.md) structure.

### -field FileCompletionInformation:30

This value is reserved for system use.

### -field FileMoveClusterInformation:31

This value is reserved for system use.

### -field FileQuotaInformation:32

A [**FILE_QUOTA_INFORMATION**](../ntifs/ns-ntifs-_file_quota_information.md) structure.

### -field FileReparsePointInformation:33

A [**FILE_REPARSE_POINT_INFORMATION**](../ntifs/ns-ntifs-_file_reparse_point_information.md) structure.

### -field FileNetworkOpenInformation:34

A [**FILE_NETWORK_OPEN_INFORMATION**](ns-wdm-_file_network_open_information.md) structure.

### -field FileAttributeTagInformation:35

A [**FILE_ATTRIBUTE_TAG_INFORMATION**](../ntddk/ns-ntddk-_file_attribute_tag_information.md) structure.

### -field FileTrackingInformation:36

This value is reserved for system use.

### -field FileIdBothDirectoryInformation:37

A [**FILE_ID_BOTH_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_id_both_dir_information.md) structure.

### -field FileIdFullDirectoryInformation:38

A [**FILE_ID_FULL_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_id_full_dir_information.md) structure.

### -field FileValidDataLengthInformation:39

A [**FILE_VALID_DATA_LENGTH_INFORMATION**](../ntddk/ns-ntddk-_file_valid_data_length_information.md) structure.

### -field FileShortNameInformation:40

A [**FILE_NAME_INFORMATION**](../ntddk/ns-ntddk-_file_name_information.md) structure.

### -field FileIoCompletionNotificationInformation:41

This value is reserved for system use. This value is available starting with Windows Vista.

### -field FileIoStatusBlockRangeInformation:42

This value is reserved for system use. This value is available starting with Windows Vista.

### -field FileIoPriorityHintInformation:43

A [**FILE_IO_PRIORITY_HINT_INFORMATION**](ns-wdm-_file_io_priority_hint_information.md) structure. This value is available starting with Windows Vista.

### -field FileSfioReserveInformation:44

This value is reserved for system use. This value is available starting with Windows Vista.

### -field FileSfioVolumeInformation:45

This value is reserved for system use. This value is available starting with Windows Vista.

### -field FileHardLinkInformation:46

A [**FILE_LINKS_INFORMATION**](../ntifs/ns-ntifs-_file_links_information.md) structure. This value is available starting with Windows Vista.

### -field FileProcessIdsUsingFileInformation:47

A **FILE_PROCESS_IDS_USING_FILE_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows Vista.

### -field FileNormalizedNameInformation:48

A [**FILE_NAME_INFORMATION**](../ntddk/ns-ntddk-_file_name_information.md) structure. This value is defined starting with Windows Vista. It is supported starting with Windows 8.

### -field FileNetworkPhysicalNameInformation:49

A [**FILE_NETWORK_PHYSICAL_NAME_INFORMATION**](../ntifs/ns-ntifs-_file_network_physical_name_information.md) structure. This value is available starting with Windows Vista.

### -field FileIdGlobalTxDirectoryInformation:50

A [**FILE_ID_GLOBAL_TX_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_id_global_tx_dir_information.md) structure. This value is available starting with Windows 7.

### -field FileIsRemoteDeviceInformation:51

A **FILE_IS_REMOTE_DEVICE_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 7.

### -field FileUnusedInformation:52

This value is reserved for system use. This value is available starting with Windows 7.

### -field FileNumaNodeInformation:53

A **FILE_NUMA_NODE_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 7.

### -field FileStandardLinkInformation:54

A **FILE_STANDARD_LINK_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 7.

### -field FileRemoteProtocolInformation:55

A [**FILE_REMOTE_PROTOCOL_INFORMATION**](../ntifs/ns-ntifs-file_remote_protocol_information.md) structure. This value is available starting with Windows 7.

### -field FileRenameInformationBypassAccessCheck:56

A [**FILE_RENAME_INFORMATION**](../ntifs/ns-ntifs-_file_rename_information.md) structure. This is a special version of the **FileRenameInformation** operation that is used by kernel-mode drivers only in order to bypass security  access checks.  This operation is only recognized by the *IOManager* and a file system should never receive it. This value is available starting with Windows 10.

### -field FileLinkInformationBypassAccessCheck:57

A [**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md) structure. This is a special version of the **FileLinkInformation** operation that is used by kernel-mode drivers only in order to bypass security access checks.  This operation is only recognized by the *IOManager* and a file system should never receive it. This value is available starting with Windows 10.

### -field FileVolumeNameInformation:58

A **FILE_VOLUME_NAME_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 10.

### -field FileIdInformation:59

A **FILE_ID_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 10.

### -field FileIdExtdDirectoryInformation:60

A **FILE_ID_EXTD_DIR_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 10.

### -field FileReplaceCompletionInformation:61

A [**FILE_COMPLETION_INFORMATION**](../ntifs/ns-ntifs-_file_completion_information.md) structure to change or remove the completion port associated with a file handle. This value is available starting with Windows 8.1.

### -field FileHardLinkFullIdInformation:62

A **FILE_LINKS_FULL_ID_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 10.

### -field FileIdExtdBothDirectoryInformation:63

A **FILE_ID_EXTD_BOTH_DIR_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 10.

### -field FileDispositionInformationEx:64

A [**FILE_DISPOSITION_INFORMATION_EX**](../ntddk/ns-ntddk-_file_disposition_information_ex.md) structure that indicates how the operating system should delete a file. This value is available starting with Windows 10, version 1709.

### -field FileRenameInformationEx:65

A [**FILE_RENAME_INFORMATION**](../ntifs/ns-ntifs-_file_rename_information.md) structure which contains additional flags. This value is available starting with Windows 10, version 1709.

### -field FileRenameInformationExBypassAccessCheck:66

A [**FILE_RENAME_INFORMATION**](../ntifs/ns-ntifs-_file_rename_information.md) structure which contains additional flags. This value is available starting with Windows 10, version 1709. This is a special version of the **FileRenameInformation** operation that is used by kernel-mode drivers only in order to bypass security access checks. This operation is only recognized by the *IOManager* and a file system should never receive it.

### -field FileDesiredStorageClassInformation:67

A [**FILE_DESIRED_STORAGE_CLASS_INFORMATION**](ne-wdm-_file_information_class.md) structure, declared in ntifs.h. This value is available starting with Windows 10, version 1709.

### -field FileStatInformation:68

A [**FILE_STAT_INFORMATION**](../ntifs/ns-ntifs-_file_stat_information.md) structure, declared in ntifs.h. This value is available starting with Windows 10, version 1709.

### -field FileMemoryPartitionInformation:69

Reserved. This value is available starting with Windows 10, version 1709.

### -field FileStatLxInformation:70

A [**FILE_STAT_LX_INFORMATION**](../ntifs/ns-ntifs-_file_stat_lx_information.md) structure, declared in ntifs.h. This information class is used for fields refer to Linux metadata used/created by the Windows Subsystem for Linux. This value is available starting with Windows 10 April 2018 Update.

### -field FileCaseSensitiveInformation:71

A [**FILE_CASE_SENSITIVE_INFORMATION**](../ntifs/ns-ntifs-_file_case_sensitive_information.md) structure, declared in ntifs.h. This value is available starting with Windows 10 April 2018 Update.

### -field FileLinkInformationEx:72

A [**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md) structure which contains additional flags. This value is available starting with Windows 10, version 1809.

### -field FileLinkInformationExBypassAccessCheck:73

A [**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md) structure which contains additional flags. This is a special version of the **FileLinkInformation** operation that is used by kernel-mode drivers only in order to bypass security  access checks. This operation is only recognized by the *IOManager* and a file system should never receive it. This value is available starting with Windows 10, version 1809.

### -field FileStorageReserveIdInformation:74

A [**FILE_SET_STORAGE_RESERVE_ID_INFORMATION**](../ntifs/ns-ntifs-_file_storage_reserve_id_information.md) structure, declared in ntifs.h. This value is available starting with Windows 10, version 1809.

### -field FileCaseSensitiveInformationForceAccessCheck:75

A [**FILE_CASE_SENSITIVE_INFORMATION**](../ntifs/ns-ntifs-_file_case_sensitive_information.md) structure, declared in ntifs.h. This is a special version of the **FileCaseSensitiveInformation** operation that is used to force the IOManager to perform access checks for the kernel-mode driver, similar to the checks that apply to a user-mode caller. This operation is only recognized by the IOManager and a file system should never receive it. This value is available starting with Windows 10, version 1809.

### -field FileKnownFolderInformation:76

A [**FILE_KNOWN_FOLDER_INFORMATION**](../ntifs/ns-ntifs-file_known_folder_information.md) structure, declared in ntifs.h. This value is available starting with Windows Server 2022.

### -field FileStatBasicInformation:77

A [**FILE_STAT_BASIC_INFORMATION**](../ntifs/ns-ntifs-file_stat_basic_information.md) structure, declared in ntifs.h. This value is available starting with Windows 11, build 26048.

### -field FileId64ExtdDirectoryInformation:78

A [**FILE_ID_64_EXTD_DIR_INFORMATION**](../ntifs/ns-ntifs-file_id_64_extd_dir_information.md) structure, declared in ntifs.h. This value is available starting with Windows 11, version 23H2.

### -field FileId64ExtdBothDirectoryInformation:79

A [**FILE_ID_64_EXTD_BOTH_DIR_INFORMATION**](../ntifs/ns-ntifs-file_id_64_extd_both_dir_information.md) structure, declared in ntifs.h. This value is available starting with Windows 11, version 23H2.

### -field FileIdAllExtdDirectoryInformation:80

A [**FILE_ID_ALL_EXTD_DIR_INFORMATION**](../ntifs/ns-ntifs-file_id_all_extd_dir_information.md) structure, declared in ntifs.h. This value is available starting with Windows 11, version 23H2.

### -field FileIdAllExtdBothDirectoryInformation:81

A [**FILE_ID_ALL_EXTD_BOTH_DIR_INFORMATION**](../ntifs/ns-ntifs-file_id_all_extd_both_dir_information.md) structure, declared in ntifs.h. This value is available starting with Windows 11, version 23H2.

### -field FileMaximumInformation

Maximum value of this enumeration. This value is available starting with Windows 7.
