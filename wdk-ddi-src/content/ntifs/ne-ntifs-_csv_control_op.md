---
UID: NE:ntifs._CSV_CONTROL_OP
title: CSV_CONTROL_OP (ntifs.h)
description: Specifies the type of cluster shared volume (CSV) control operation to use with the FSCTL_CSV_CONTROL control code.
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["CSV_CONTROL_OP enumeration"]
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
targetos: Windows
f1_keywords:
 - _CSV_CONTROL_OP
 - ntifs/_CSV_CONTROL_OP
 - PCSV_CONTROL_OP
 - ntifs/PCSV_CONTROL_OP
 - CSV_CONTROL_OP
 - ntifs/CSV_CONTROL_OP
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _CSV_CONTROL_OP
 - PCSV_CONTROL_OP
 - CSV_CONTROL_OP
---

# CSV_CONTROL_OP enumeration

## -description

Specifies the type of cluster shared volume (CSV) control operation to use with the [FSCTL_CSV_CONTROL](/windows/win32/api/winioctl/ni-winioctl-fsctl_csv_control) control code.

## -enum-fields

### -field CsvControlStartRedirectFile:0x02

Starts CSV file redirection.

### -field CsvControlStopRedirectFile:0x03

Stops CSV file redirection.

### -field CsvControlQueryRedirectState:0x04

Search for state redirection. When this value is specified, the [CSV_QUERY_REDIRECT_STATE](/windows/win32/api/winioctl/ns-winioctl-csv_query_redirect_state) structure must also be used.

### -field CsvControlQueryFileRevision:0x06

Search for file revision. When this value is specified, the [CSV_QUERY_FILE_REVISION](/windows/win32/api/winioctl/ns-winioctl-csv_query_file_revision) structure must also be used.

### -field CsvControlQueryMdsPath:0x08

Search for MDS path. When this value is specified, the [CSV_QUERY_MDS_PATH](/windows/win32/api/winioctl/ns-winioctl-csv_query_mds_path) structure must also be used.

### -field CsvControlQueryFileRevisionFileId128:0x09

Search for 128-bit file revision. When this value is specified, the CSV_QUERY_FILE_REVISION_FILE_ID_128 structure must also be used.

### -field CsvControlQueryVolumeRedirectState:0x0a

Search for volume state redirection. When this value is specified, the CSV_QUERY_VOLUME_REDIRECT_STATE structure must also be used.

### -field CsvControlEnableUSNRangeModificationTracking:0x0d

Enable USN range tracking.

### -field CsvControlMarkHandleLocalVolumeMount:0x0e

When a VHD file is about to be loopback mounted, marks a handle and requests that CVSFS to fail I/Os and invalidate handles after a short timeout (currently 20 seconds) if no I/Os make progress.

### -field CsvControlUnmarkHandleLocalVolumeMount:0x0f

When a VHD file is about to be loopback unmounted, unmarks a handle that had been previously marked by **CsvControlMarkHandleLocalVolumeMount**.

### -field CsvControlGetCsvFsMdsPathV2:0x12

Search for version 2 of the MDS path. When this value is specified, the CSV_QUERY_MDS_PATH_V2 structure must also be used.

### -field CsvControlDisableCaching:0x13

Disables caching of the CSV file.

### -field CsvControlEnableCaching:0x14

Enables caching of the CSV file.

### -field CsvControlStartForceDFO:0x15

Forces CSVFS to start forwarding I/O down-level on a down-level file object (DFO). See Remarks for details.

### -field CsvControlStopForceDFO:0x16

Stop forcing CSVFS's forwarding of I/O on a DFO. See Remarks for details.

### -field CsvControlQueryMdsPathNoPause:0x17

Similar to CsvControlQueryMdsPath. Search for MDS path, but if the CSV volume is paused at the moment of the request, set **MdsNodeId** to 0xFFFFFFFF instead of returning the last coordinating node. This allows the client to detect that the coordinating node might be changing. When CsvControlQueryMdsPathNoPause is specified, the [CSV_QUERY_MDS_PATH](/windows/win32/api/winioctl/ns-winioctl-csv_query_mds_path) structure must also be used.

### -field CsvControlSetVolumeId:0x18

Set the CSV Volume GUID. See Remarks for details.

### -field CsvControlQueryVolumeId:0x19

Query whether the CSV Volume GUID is available. See Remarks for details.

## -remarks

An alternative to calling the [FSCTL_CSV_CONTROL](/windows/win32/api/winioctl/ni-winioctl-fsctl_csv_control) control code with this enumeration is to use the [CSV_CONTROL_PARAM](/windows/win32/api/winioctl/ns-winioctl-csv_control_param) structure, which encapsulates a member of this enumeration type.

### CsvControlStartForceDFO and CsvControlStopForceDFO

When a file object is opened on CSVFS, CSVFS opens on the down-level file system (NTFS or REFS) a down-level file object (DFO) matching every user open. That file object is opened as a part of an application opening a file on CSVFS and is closed when the application closes the handle for the file object on CSVFS. Internally CSVFS opens an additional file object called paging file object (PFO) that is shared among all opens of the same file on CSVFS. By default, CSVFS uses it for many operations, such as the following:

* Oplock negotiation
* Byte range locks
* Forwarding of paging I/O

Some filtering solutions might mark the handle in a special way, and then expect that all reads and writes should be forwarded down-level by CSVFS on the matching DFO. An application can force CSVFS to start forwarding IO down-level on DFO by sending **CsvControlStartForceDFO**. Later on, the application can use **CsvControlStopForceDFO** to revert to the default behavior. Closing the handle that was used to send **CsvControlStartForceDFO** will implicitly revert back as if application sent **CsvControlStopForceDFO**.

### CsvControlSetVolumeId and CsvControlQueryVolumeId

These controls allow file system minifilters attached to the down-level file system below CSVFS to learn the CSV Volume GUID. The Cluster Physical Disk Resource sets this GUID after the down-level file system is mounted so it is not available if the filter attaches during mount. During filter attach, the file system minifilter can issue CsvControlQueryVolumeId to query whether the GUID is already available. Control has to be sent to the top of stack to make sure *csvflt* receives it. If the volume GUID is not available yet, then *csvflt* will return STATUS_UNSUCCESSFUL. The filter should not fail to attach if the volume GUID is not yet available.

At a later point, the Physical Disk Resource will send CsvControlSetVolumeId with the volume GUID. Every filter on the stack can use the CsvControlSetVolumeId control to store the volume GUID. Filters must not complete this control. Instead they should allow it to go down the stack, allowing other filters the opportunity to store the GUID.

## -see-also

[File Management Enumerations](/windows/win32/fileio/file-management-enumerations)

[CSV_CONTROL_PARAM](/windows/win32/api/winioctl/ns-winioctl-csv_control_param)

[CSV_QUERY_FILE_REVISION](/windows/win32/api/winioctl/ns-winioctl-csv_query_file_revision)

[CSV_QUERY_MDS_PATH](/windows/win32/api/winioctl/ns-winioctl-csv_query_mds_path)

[CSV_QUERY_REDIRECT_STATE](/windows/win32/api/winioctl/ns-winioctl-csv_query_redirect_state)

[FSCTL_CSV_CONTROL](/windows/win32/api/winioctl/ni-winioctl-fsctl_csv_control)
