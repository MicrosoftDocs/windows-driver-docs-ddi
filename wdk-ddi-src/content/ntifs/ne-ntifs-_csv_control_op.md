---
UID: NE:ntifs._CSV_CONTROL_OP
title: _CSV_CONTROL_OP (ntifs.h)
description: Specifies the type of cluster shared volume (CSV) control operation to use with the FSCTL_CSV_CONTROL control code.
tech.root: ifsk
ms.assetid: a08a089b-44a0-45b7-98e3-8d82b3edef4b
ms.date: 10/21/2019
keywords: ["CSV_CONTROL_OP enumeration"]
f1_keywords:
 - "ntifs/_CSV_CONTROL_OP"
 - "_CSV_CONTROL_OP"
ms.keywords: _CSV_CONTROL_OP, CSV_CONTROL_OP, *PCSV_CONTROL_OP, 
req.header: ntifs.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: CSV_CONTROL_OP, *PCSV_CONTROL_OP
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- ntifs.h
api_name: 
- _CSV_CONTROL_OP
targetos: Windows
---

# _CSV_CONTROL_OP enumeration

## -description

Specifies the type of cluster shared volume (CSV) control operation to use with the [FSCTL_CSV_CONTROL](https://docs.microsoft.com/windows/win32/api/winioctl/ni-winioctl-fsctl_csv_control) control code.

## -enum-fields

### -field CsvControlStartRedirectFile

Starts CSV file redirection.

### -field CsvControlStopRedirectFile

Stops CSV file redirection.

### -field CsvControlQueryRedirectState

Search for state redirection. When this value is specified, the [CSV_QUERY_REDIRECT_STATE](https://docs.microsoft.com/windows/win32/api/winioctl/ns-winioctl-csv_query_redirect_state) structure must also be used.

### -field CsvControlQueryFileRevision  

Search for file revision. When this value is specified, the [CSV_QUERY_FILE_REVISION](https://docs.microsoft.com/windows/win32/api/winioctl/ns-winioctl-csv_query_file_revision) structure must also be used.

### -field CsvControlQueryMdsPath

Search for MDS path. When this value is specified, the [CSV_QUERY_MDS_PATH](https://docs.microsoft.com/windows/win32/api/winioctl/ns-winioctl-csv_query_mds_path) structure must also be used.

### -field CsvControlQueryFileRevisionFileId128

Search for 128-bit file revision. When this value is specified, the CSV_QUERY_FILE_REVISION_FILE_ID_128 structure must also be used.

### -field CsvControlQueryVolumeRedirectState

Search for volume state redirection. When this value is specified, the CSV_QUERY_VOLUME_REDIRECT_STATE structure must also be used.

### -field CsvControlEnableUSNRangeModificationTracking

Enable USN range tracking.

### -field CsvControlMarkHandleLocalVolumeMount

When a VHD file is about to be loopback mounted, marks a handle and requests that CVSFS to fail I/Os and invalidate handles after a short timeout (currently 20 seconds) if no I/Os make progress.

### -field CsvControlUnmarkHandleLocalVolumeMount

When a VHD file is about to be loopback unmounted, unmarks a handle that had been previously marked by **CsvControlMarkHandleLocalVolumeMount**.

### -field CsvControlGetCsvFsMdsPathV2

Search for version 2 of the MDS path. When this value is specified, the CSV_QUERY_MDS_PATH_V2 structure must also be used.

### -field CsvControlDisableCaching

Disables caching of the CSV file.

### -field CsvControlEnableCaching

Enables caching of the CSV file.

## -remarks

An alternative to calling the [FSCTL_CSV_CONTROL](https://docs.microsoft.com/windows/win32/api/winioctl/ni-winioctl-fsctl_csv_control) control code with this enumeration is to use the [CSV_CONTROL_PARAM](https://docs.microsoft.com/windows/win32/api/winioctl/ns-winioctl-csv_control_param) structure, which encapsulates a member of this enumeration type.

## -see-also

[File Management Enumerations](https://docs.microsoft.com/windows/desktop/FileIO/file-management-enumerations)

[CSV_CONTROL_PARAM](https://docs.microsoft.com/windows/win32/api/winioctl/ns-winioctl-csv_control_param)

[CSV_QUERY_FILE_REVISION](https://docs.microsoft.com/windows/win32/api/winioctl/ns-winioctl-csv_query_file_revision)

[CSV_QUERY_MDS_PATH](https://docs.microsoft.com/windows/win32/api/winioctl/ns-winioctl-csv_query_mds_path)

[CSV_QUERY_REDIRECT_STATE](https://docs.microsoft.com/windows/win32/api/winioctl/ns-winioctl-csv_query_redirect_state)

[FSCTL_CSV_CONTROL](https://docs.microsoft.com/windows/win32/api/winioctl/ni-winioctl-fsctl_csv_control)
