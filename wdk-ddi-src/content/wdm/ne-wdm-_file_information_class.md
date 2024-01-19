---
UID: NE:wdm._FILE_INFORMATION_CLASS
title: _FILE_INFORMATION_CLASS (wdm.h)
description: A value that specifies which structure to use to query or set information for a file object.
tech.root: ifsk
ms.date: 08/17/2023
keywords: ["FILE_INFORMATION_CLASS enumeration"]
ms.keywords: "*PFILE_INFORMATION_CLASS, FILE_INFORMATION_CLASS, FILE_INFORMATION_CLASS enumeration [Installable File System Drivers], FileAccessInformation, FileAlignmentInformation, FileAllInformation, FileAllocationInformation, FileAlternateNameInformation, FileAttributeTagInformation, FileBasicInformation, FileBothDirectoryInformation, FileCompletionInformation, FileCompressionInformation, FileDirectoryInformation, FileDispositionInformation, FileDispositionInformationEx, FileEaInformation, FileEndOfFileInformation, FileFullDirectoryInformation, FileFullEaInformation, FileHardLinkFullIdInformation, FileHardLinkInformation, FileIdBothDirectoryInformation, FileIdExtdBothDirectoryInformation, FileIdExtdDirectoryInformation, FileIdFullDirectoryInformation, FileIdGlobalTxDirectoryInformation, FileIdInformation, FileInternalInformation, FileIoCompletionNotificationInformation, FileIoPriorityHintInformation, FileIoStatusBlockRangeInformation, FileIsRemoteDeviceInformation, FileLinkInformation, FileLinkInformationBypassAccessCheck, FileMailslotQueryInformation, FileMailslotSetInformation, FileMaximumInformation, FileModeInformation, FileMoveClusterInformation, FileNameInformation, FileNamesInformation, FileNetworkOpenInformation, FileNetworkPhysicalNameInformation, FileNormalizedNameInformation, FileNumaNodeInformation, FileObjectIdInformation, FilePipeInformation, FilePipeLocalInformation, FilePipeRemoteInformation, FilePositionInformation, FileProcessIdsUsingFileInformation, FileQuotaInformation, FileRemoteProtocolInformation, FileRenameInformation, FileRenameInformationBypassAccessCheck, FileRenameInformationEx, FileRenameInformationExBypassAccessCheck, FileReparsePointInformation, FileReplaceCompletionInformation, FileSfioReserveInformation, FileSfioVolumeInformation, FileShortNameInformation, FileStandardInformation, FileStandardLinkInformation, FileStreamInformation, FileTrackingInformation, FileUnusedInformation, FileValidDataLengthInformation, FileVolumeNameInformation, PFILE_INFORMATION_CLASS, PFILE_INFORMATION_CLASS enumeration pointer [Installable File System Drivers], _FILE_INFORMATION_CLASS, ifsk.file_information_class, ntifs/ FileDispositionInformationEx, ntifs/ FileIdExtdBothDirectoryInformation, ntifs/FILE_INFORMATION_CLASS, ntifs/FileAccessInformation, ntifs/FileAlignmentInformation, ntifs/FileAllInformation, ntifs/FileAllocationInformation, ntifs/FileAlternateNameInformation, ntifs/FileAttributeTagInformation, ntifs/FileBasicInformation, ntifs/FileBothDirectoryInformation, ntifs/FileCompletionInformation, ntifs/FileCompressionInformation, ntifs/FileDirectoryInformation, ntifs/FileDispositionInformation, ntifs/FileEaInformation, ntifs/FileEndOfFileInformation, ntifs/FileFullDirectoryInformation, ntifs/FileFullEaInformation, ntifs/FileHardLinkFullIdInformation, ntifs/FileHardLinkInformation, ntifs/FileIdBothDirectoryInformation, ntifs/FileIdExtdDirectoryInformation, ntifs/FileIdFullDirectoryInformation, ntifs/FileIdGlobalTxDirectoryInformation, ntifs/FileIdInformation, ntifs/FileInternalInformation, ntifs/FileIoCompletionNotificationInformation, ntifs/FileIoPriorityHintInformation, ntifs/FileIoStatusBlockRangeInformation, ntifs/FileIsRemoteDeviceInformation, ntifs/FileLinkInformation, ntifs/FileLinkInformationBypassAccessCheck, ntifs/FileMailslotQueryInformation, ntifs/FileMailslotSetInformation, ntifs/FileMaximumInformation, ntifs/FileModeInformation, ntifs/FileMoveClusterInformation, ntifs/FileNameInformation, ntifs/FileNamesInformation, ntifs/FileNetworkOpenInformation, ntifs/FileNetworkPhysicalNameInformation, ntifs/FileNormalizedNameInformation, ntifs/FileNumaNodeInformation, ntifs/FileObjectIdInformation, ntifs/FilePipeInformation, ntifs/FilePipeLocalInformation, ntifs/FilePipeRemoteInformation, ntifs/FilePositionInformation, ntifs/FileProcessIdsUsingFileInformation, ntifs/FileQuotaInformation, ntifs/FileRemoteProtocolInformation, ntifs/FileRenameInformation, ntifs/FileRenameInformationBypassAccessCheck, ntifs/FileRenameInformationEx, ntifs/FileRenameInformationExBypassAccessCheck, ntifs/FileReparsePointInformation, ntifs/FileReplaceCompletionInformation, ntifs/FileSfioReserveInformation, ntifs/FileSfioVolumeInformation, ntifs/FileShortNameInformation, ntifs/FileStandardInformation, ntifs/FileStandardLinkInformation, ntifs/FileStreamInformation, ntifs/FileTrackingInformation, ntifs/FileUnusedInformation, ntifs/FileValidDataLengthInformation, ntifs/FileVolumeNameInformation, ntifs/PFILE_INFORMATION_CLASS, wdm/ FileDispositionInformationEx, wdm/ FileIdExtdBothDirectoryInformation, wdm/FILE_INFORMATION_CLASS, wdm/FileAccessInformation, wdm/FileAlignmentInformation, wdm/FileAllInformation, wdm/FileAllocationInformation, wdm/FileAlternateNameInformation, wdm/FileAttributeTagInformation, wdm/FileBasicInformation, wdm/FileBothDirectoryInformation, wdm/FileCompletionInformation, wdm/FileCompressionInformation, wdm/FileDirectoryInformation, wdm/FileDispositionInformation, wdm/FileEaInformation, wdm/FileEndOfFileInformation, wdm/FileFullDirectoryInformation, wdm/FileFullEaInformation, wdm/FileHardLinkFullIdInformation, wdm/FileHardLinkInformation, wdm/FileIdBothDirectoryInformation, wdm/FileIdExtdDirectoryInformation, wdm/FileIdFullDirectoryInformation, wdm/FileIdGlobalTxDirectoryInformation, wdm/FileIdInformation, wdm/FileInternalInformation, wdm/FileIoCompletionNotificationInformation, wdm/FileIoPriorityHintInformation, wdm/FileIoStatusBlockRangeInformation, wdm/FileIsRemoteDeviceInformation, wdm/FileLinkInformation, wdm/FileLinkInformationBypassAccessCheck, wdm/FileMailslotQueryInformation, wdm/FileMailslotSetInformation, wdm/FileMaximumInformation, wdm/FileModeInformation, wdm/FileMoveClusterInformation, wdm/FileNameInformation, wdm/FileNamesInformation, wdm/FileNetworkOpenInformation, wdm/FileNetworkPhysicalNameInformation, wdm/FileNormalizedNameInformation, wdm/FileNumaNodeInformation, wdm/FileObjectIdInformation, wdm/FilePipeInformation, wdm/FilePipeLocalInformation, wdm/FilePipeRemoteInformation, wdm/FilePositionInformation, wdm/FileProcessIdsUsingFileInformation, wdm/FileQuotaInformation, wdm/FileRemoteProtocolInformation, wdm/FileRenameInformation, wdm/FileRenameInformationBypassAccessCheck, wdm/FileRenameInformationEx, wdm/FileRenameInformationExBypassAccessCheck, wdm/FileReparsePointInformation, wdm/FileReplaceCompletionInformation, wdm/FileSfioReserveInformation, wdm/FileSfioVolumeInformation, wdm/FileShortNameInformation, wdm/FileStandardInformation, wdm/FileStandardLinkInformation, wdm/FileStreamInformation, wdm/FileTrackingInformation, wdm/FileUnusedInformation, wdm/FileValidDataLengthInformation, wdm/FileVolumeNameInformation, wdm/PFILE_INFORMATION_CLASS"
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

# FILE_INFORMATION_CLASS enumeration

## -description

A value that specifies which structure to use to query or set information for a file object.

## -enum-fields

### -field FileDirectoryInformation

A [**FILE_DIRECTORY_INFORMATION**](../ntifs/ns-ntifs-_file_directory_information.md) structure.

### -field FileFullDirectoryInformation

A [**FILE_FULL_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_full_dir_information.md) structure.

### -field FileBothDirectoryInformation

A [**FILE_BOTH_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_both_dir_information.md) structure.

### -field FileBasicInformation

A [**FILE_BASIC_INFORMATION**](ns-wdm-_file_basic_information.md) structure.

### -field FileStandardInformation

A [**FILE_STANDARD_INFORMATION**](ns-wdm-_file_standard_information.md) structure.

### -field FileInternalInformation

A [**FILE_INTERNAL_INFORMATION**](../ntifs/ns-ntifs-_file_internal_information.md) structure.

### -field FileEaInformation

A [**FILE_EA_INFORMATION**](../ntifs/ns-ntifs-_file_ea_information.md) structure.

### -field FileAccessInformation

A [**FILE_ACCESS_INFORMATION**](../ntifs/ns-ntifs-_file_access_information.md) structure.

### -field FileNameInformation

A [**FILE_NAME_INFORMATION**](../ntddk/ns-ntddk-_file_name_information.md) structure.

### -field FileRenameInformation

A [**FILE_RENAME_INFORMATION**](../ntifs/ns-ntifs-_file_rename_information.md) structure.

### -field FileLinkInformation

A [**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md) structure.

### -field FileNamesInformation

A [**FILE_NAMES_INFORMATION**](../ntifs/ns-ntifs-_file_names_information.md) structure.

### -field FileDispositionInformation

A [**FILE_DISPOSITION_INFORMATION**](../ntddk/ns-ntddk-_file_disposition_information.md) structure.

### -field FilePositionInformation

A [**FILE_POSITION_INFORMATION**](ns-wdm-_file_position_information.md) structure.

### -field FileFullEaInformation

A [**FILE_FULL_EA_INFORMATION**](ns-wdm-_file_full_ea_information.md) structure.

### -field FileModeInformation

A [**FILE_MODE_INFORMATION**](../ntifs/ns-ntifs-_file_mode_information.md) structure.

### -field FileAlignmentInformation

A [**FILE_ALIGNMENT_INFORMATION**](../ntddk/ns-ntddk-_file_alignment_information.md) structure.

### -field FileAllInformation

A [**FILE_ALL_INFORMATION**](../ntifs/ns-ntifs-_file_all_information.md) structure.

### -field FileAllocationInformation

A [**FILE_ALLOCATION_INFORMATION**](../ntifs/ns-ntifs-_file_allocation_information.md) structure.

### -field FileEndOfFileInformation

A [**FILE_END_OF_FILE_INFORMATION**](../ntddk/ns-ntddk-_file_end_of_file_information.md) structure.

### -field FileAlternateNameInformation

A [**FILE_NAME_INFORMATION**](../ntddk/ns-ntddk-_file_name_information.md) structure.

### -field FileStreamInformation

A message buffer that contains one or more [**FILE_STREAM_INFORMATION**](../ntifs/ns-ntifs-_file_stream_information.md) structures.

### -field FilePipeInformation

A [**FILE_PIPE_INFORMATION**](../ntifs/ns-ntifs-_file_pipe_information.md) structure.

### -field FilePipeLocalInformation

A [**FILE_PIPE_LOCAL_INFORMATION**](../ntifs/ns-ntifs-_file_pipe_local_information.md) structure.

### -field FilePipeRemoteInformation

A [**FILE_PIPE_REMOTE_INFORMATION**](../ntifs/ns-ntifs-_file_pipe_remote_information.md) structure.

### -field FileMailslotQueryInformation

A [**FILE_MAILSLOT_QUERY_INFORMATION**](../ntifs/ns-ntifs-_file_mailslot_query_information.md) structure.

### -field FileMailslotSetInformation

A [**FILE_MAILSLOT_SET_INFORMATION**](../ntifs/ns-ntifs-_file_mailslot_set_information.md) structure.

### -field FileCompressionInformation

A [**FILE_COMPRESSION_INFORMATION**](../ntifs/ns-ntifs-_file_compression_information.md) structure.

### -field FileObjectIdInformation

A [**FILE_OBJECTID_INFORMATION**](../ntifs/ns-ntifs-_file_objectid_information.md) structure.

### -field FileCompletionInformation

This value is reserved for system use.

### -field FileMoveClusterInformation

This value is reserved for system use.

### -field FileQuotaInformation

A [**FILE_QUOTA_INFORMATION**](../ntifs/ns-ntifs-_file_quota_information.md) structure.

### -field FileReparsePointInformation

A [**FILE_REPARSE_POINT_INFORMATION**](../ntifs/ns-ntifs-_file_reparse_point_information.md) structure.

### -field FileNetworkOpenInformation

A [**FILE_NETWORK_OPEN_INFORMATION**](ns-wdm-_file_network_open_information.md) structure.

### -field FileAttributeTagInformation

A [**FILE_ATTRIBUTE_TAG_INFORMATION**](../ntddk/ns-ntddk-_file_attribute_tag_information.md) structure.

### -field FileTrackingInformation

This value is reserved for system use.

### -field FileIdBothDirectoryInformation

A [**FILE_ID_BOTH_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_id_both_dir_information.md) structure.

### -field FileIdFullDirectoryInformation

A [**FILE_ID_FULL_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_id_full_dir_information.md) structure.

### -field FileValidDataLengthInformation

A [**FILE_VALID_DATA_LENGTH_INFORMATION**](../ntddk/ns-ntddk-_file_valid_data_length_information.md) structure.

### -field FileShortNameInformation

A [**FILE_NAME_INFORMATION**](../ntddk/ns-ntddk-_file_name_information.md) structure.

### -field FileIoCompletionNotificationInformation

This value is reserved for system use. This value is available starting with Windows Vista.

### -field FileIoStatusBlockRangeInformation

This value is reserved for system use. This value is available starting with Windows Vista.

### -field FileIoPriorityHintInformation

A [**FILE_IO_PRIORITY_HINT_INFORMATION**](ns-wdm-_file_io_priority_hint_information.md) structure. This value is available starting with Windows Vista.

### -field FileSfioReserveInformation

This value is reserved for system use. This value is available starting with Windows Vista.

### -field FileSfioVolumeInformation

This value is reserved for system use. This value is available starting with Windows Vista.

### -field FileHardLinkInformation

A [**FILE_LINKS_INFORMATION**](../ntifs/ns-ntifs-_file_links_information.md) structure. This value is available starting with Windows Vista.

### -field FileProcessIdsUsingFileInformation

A **FILE_PROCESS_IDS_USING_FILE_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows Vista.

### -field FileNormalizedNameInformation

A [**FILE_NAME_INFORMATION**](../ntddk/ns-ntddk-_file_name_information.md) structure. This value is defined starting with Windows Vista. It is supported starting with Windows 8.

### -field FileNetworkPhysicalNameInformation

A [**FILE_NETWORK_PHYSICAL_NAME_INFORMATION**](../ntifs/ns-ntifs-_file_network_physical_name_information.md) structure. This value is available starting with Windows Vista.

### -field FileIdGlobalTxDirectoryInformation

A [**FILE_ID_GLOBAL_TX_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_id_global_tx_dir_information.md) structure. This value is available starting with Windows 7.

### -field FileIsRemoteDeviceInformation

A **FILE_IS_REMOTE_DEVICE_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 7.

### -field FileUnusedInformation

This value is reserved for system use. This value is available starting with Windows 7.

### -field FileNumaNodeInformation

A **FILE_NUMA_NODE_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 7.

### -field FileStandardLinkInformation

A **FILE_STANDARD_LINK_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 7.

### -field FileRemoteProtocolInformation

A [**FILE_REMOTE_PROTOCOL_INFORMATION**](../ntifs/ns-ntifs-file_remote_protocol_information.md) structure. This value is available starting with Windows 7.

### -field FileRenameInformationBypassAccessCheck

A [**FILE_RENAME_INFORMATION**](../ntifs/ns-ntifs-_file_rename_information.md) structure. This is a special version of the **FileRenameInformation** operation that is used by kernel-mode drivers only in order to bypass security  access checks.  This operation is only recognized by the *IOManager* and a file system should never receive it. This value is available starting with Windows 10.

### -field FileLinkInformationBypassAccessCheck

A [**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md) structure. This is a special version of the **FileLinkInformation** operation that is used by kernel-mode drivers only in order to bypass security access checks.  This operation is only recognized by the *IOManager* and a file system should never receive it. This value is available starting with Windows 10.

### -field FileVolumeNameInformation

A **FILE_VOLUME_NAME_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 10.

### -field FileIdInformation

A **FILE_ID_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 10.

### -field FileIdExtdDirectoryInformation

A **FILE_ID_EXTD_DIR_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 10.

### -field FileReplaceCompletionInformation

A [**FILE_COMPLETION_INFORMATION**](../ntifs/ns-ntifs-_file_completion_information.md) structure to change or remove the completion port associated with a file handle. This value is available starting with Windows 8.1.

### -field FileHardLinkFullIdInformation

A **FILE_LINKS_FULL_ID_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 10.

### -field FileIdExtdBothDirectoryInformation

A **FILE_ID_EXTD_BOTH_DIR_INFORMATION** structure. This value is reserved for system use. This value is available starting with Windows 10.

### -field FileDispositionInformationEx

A [**FILE_DISPOSITION_INFORMATION_EX**](../ntddk/ns-ntddk-_file_disposition_information_ex.md) structure that indicates how the operating system should delete a file. This value is available starting with Windows 10, version 1709.

### -field FileRenameInformationEx

A [**FILE_RENAME_INFORMATION**](../ntifs/ns-ntifs-_file_rename_information.md) structure which contains additional flags. This value is available starting with Windows 10, version 1709.

### -field FileRenameInformationExBypassAccessCheck

A [**FILE_RENAME_INFORMATION**](../ntifs/ns-ntifs-_file_rename_information.md) structure which contains additional flags. This value is available starting with Windows 10, version 1709. This is a special version of the **FileRenameInformation** operation that is used by kernel-mode drivers only in order to bypass security access checks. This operation is only recognized by the *IOManager* and a file system should never receive it.

### -field FileDesiredStorageClassInformation

A [**FILE_DESIRED_STORAGE_CLASS_INFORMATION**](ne-wdm-_file_information_class.md) structure, declared in ntifs.h. This value is available starting with Windows 10, version 1709.

### -field FileStatInformation

A [**FILE_STAT_INFORMATION**](../ntifs/ns-ntifs-_file_stat_information.md) structure, declared in ntifs.h. This value is available starting with Windows 10, version 1709.

### -field FileMemoryPartitionInformation

Reserved. This value is available starting with Windows 10, version 1709.

### -field FileStatLxInformation

A [**FILE_STAT_LX_INFORMATION**](../ntifs/ns-ntifs-_file_stat_lx_information.md) structure, declared in ntifs.h. This information class is used for fields refer to Linux metadata used/created by the Windows Subsystem for Linux. This value is available starting with Windows 10 April 2018 Update.

### -field FileCaseSensitiveInformation

A [**FILE_CASE_SENSITIVE_INFORMATION**](../ntifs/ns-ntifs-_file_case_sensitive_information.md) structure, declared in ntifs.h. This value is available starting with Windows 10 April 2018 Update.

### -field FileLinkInformationEx

A [**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md) structure which contains additional flags. This value is available starting with Windows 10, version 1809.

### -field FileLinkInformationExBypassAccessCheck

A [**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md) structure which contains additional flags. This is a special version of the **FileLinkInformation** operation that is used by kernel-mode drivers only in order to bypass security  access checks. This operation is only recognized by the *IOManager* and a file system should never receive it. This value is available starting with Windows 10, version 1809.

### -field FileStorageReserveIdInformation

A [**FILE_SET_STORAGE_RESERVE_ID_INFORMATION**](../ntifs/ns-ntifs-_file_storage_reserve_id_information.md) structure, declared in ntifs.h. This value is available starting with Windows 10, version 1809.

### -field FileCaseSensitiveInformationForceAccessCheck

A [**FILE_CASE_SENSITIVE_INFORMATION**](../ntifs/ns-ntifs-_file_case_sensitive_information.md) structure, declared in ntifs.h. This is a special version of the **FileCaseSensitiveInformation** operation that is used to force the IOManager to perform access checks for the kernel-mode driver, similar to the checks that apply to a user-mode caller. This operation is only recognized by the IOManager and a file system should never receive it. This value is available starting with Windows 10, version 1809.

### -field FileKnownFolderInformation

A [**FILE_KNOWN_FOLDER_INFORMATION**](../ntifs/ns-ntifs-file_known_folder_information.md) structure, declared in ntifs.h. This value is available starting with Windows Server 2022.

### -field FileStatBasicInformation

A **FILE_STAT_BASIC_INFORMATION** structure, declared in ntifs.h. This value is available starting with Windows 11, version 23H2.

### -field FileId64ExtdDirectoryInformation

A **FILE_ID_64_EXTD_DIRECTORY_INFORMATION** structure, declared in ntifs.h. This value is available starting with Windows 11, version 23H2.

### -field FileId64ExtdBothDirectoryInformation

A **FILE_ID_64_EXTD_BOTH_DIRECTORY_INFORMATION** structure, declared in ntifs.h. This value is available starting with Windows 11, version 23H2.

### -field FileIdAllExtdDirectoryInformation

A **FILE_ID_ALL_EXTD_DIRECTORY_INFORMATION** structure, declared in ntifs.h. This value is available starting with Windows 11, version 23H2.

### -field FileIdAllExtdBothDirectoryInformation

A **FILE_ID_ALL_EXTD_BOTH_DIRECTORY_INFORMATION** structure, declared in ntifs.h. This value is available starting with Windows 11, version 23H2.

### -field FileMaximumInformation

This value is reserved for system use. This value is available starting with Windows 7.

## -syntax

```cpp
typedef enum _FILE_INFORMATION_CLASS {
    FileDirectoryInformation                         = 1,
    FileFullDirectoryInformation,                   // 2
    FileBothDirectoryInformation,                   // 3
    FileBasicInformation,                           // 4
    FileStandardInformation,                        // 5
    FileInternalInformation,                        // 6
    FileEaInformation,                              // 7
    FileAccessInformation,                          // 8
    FileNameInformation,                            // 9
    FileRenameInformation,                          // 10
    FileLinkInformation,                            // 11
    FileNamesInformation,                           // 12
    FileDispositionInformation,                     // 13
    FilePositionInformation,                        // 14
    FileFullEaInformation,                          // 15
    FileModeInformation,                            // 16
    FileAlignmentInformation,                       // 17
    FileAllInformation,                             // 18
    FileAllocationInformation,                      // 19
    FileEndOfFileInformation,                       // 20
    FileAlternateNameInformation,                   // 21
    FileStreamInformation,                          // 22
    FilePipeInformation,                            // 23
    FilePipeLocalInformation,                       // 24
    FilePipeRemoteInformation,                      // 25
    FileMailslotQueryInformation,                   // 26
    FileMailslotSetInformation,                     // 27
    FileCompressionInformation,                     // 28
    FileObjectIdInformation,                        // 29
    FileCompletionInformation,                      // 30
    FileMoveClusterInformation,                     // 31
    FileQuotaInformation,                           // 32
    FileReparsePointInformation,                    // 33
    FileNetworkOpenInformation,                     // 34
    FileAttributeTagInformation,                    // 35
    FileTrackingInformation,                        // 36
    FileIdBothDirectoryInformation,                 // 37
    FileIdFullDirectoryInformation,                 // 38
    FileValidDataLengthInformation,                 // 39
    FileShortNameInformation,                       // 40
    FileIoCompletionNotificationInformation,        // 41
    FileIoStatusBlockRangeInformation,              // 42
    FileIoPriorityHintInformation,                  // 43
    FileSfioReserveInformation,                     // 44
    FileSfioVolumeInformation,                      // 45
    FileHardLinkInformation,                        // 46
    FileProcessIdsUsingFileInformation,             // 47
    FileNormalizedNameInformation,                  // 48
    FileNetworkPhysicalNameInformation,             // 49
    FileIdGlobalTxDirectoryInformation,             // 50
    FileIsRemoteDeviceInformation,                  // 51
    FileUnusedInformation,                          // 52
    FileNumaNodeInformation,                        // 53
    FileStandardLinkInformation,                    // 54
    FileRemoteProtocolInformation,                  // 55

        //
        //  These are special versions of these operations (defined earlier)
        //  which can be used by kernel mode drivers only to bypass security
        //  access checks for Rename and HardLink operations.  These operations
        //  are only recognized by the IOManager, a file system should never
        //  receive these.
        //

    FileRenameInformationBypassAccessCheck,         // 56
    FileLinkInformationBypassAccessCheck,           // 57

        //
        // End of special information classes reserved for IOManager.
        //

    FileVolumeNameInformation,                      // 58
    FileIdInformation,                              // 59
    FileIdExtdDirectoryInformation,                 // 60
    FileReplaceCompletionInformation,               // 61
    FileHardLinkFullIdInformation,                  // 62
    FileIdExtdBothDirectoryInformation,             // 63
    FileDispositionInformationEx,                   // 64
    FileRenameInformationEx,                        // 65
    FileRenameInformationExBypassAccessCheck,       // 66
    FileDesiredStorageClassInformation,             // 67
    FileStatInformation,                            // 68
    FileMemoryPartitionInformation,                 // 69
    FileStatLxInformation,                          // 70
    FileCaseSensitiveInformation,                   // 71
    FileLinkInformationEx,                          // 72
    FileLinkInformationExBypassAccessCheck,         // 73
    FileStorageReserveIdInformation,                // 74
    FileCaseSensitiveInformationForceAccessCheck,   // 75
    FileKnownFolderInformation,                     // 76
    FileStatBasicInformation,                       // 77
    FileId64ExtdDirectoryInformation,               // 78
    FileId64ExtdBothDirectoryInformation,           // 79
    FileIdAllExtdDirectoryInformation,              // 80
    FileIdAllExtdBothDirectoryInformation,          // 81
 
    FileMaximumInformation
} FILE_INFORMATION_CLASS, *PFILE_INFORMATION_CLASS;
```
