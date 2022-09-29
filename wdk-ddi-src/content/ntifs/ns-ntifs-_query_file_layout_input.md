---
UID: NS:ntifs._QUERY_FILE_LAYOUT_INPUT
title: QUERY_FILE_LAYOUT_INPUT (ntifs.h)
description: The QUERY_FILE_LAYOUT_INPUT structure selects which file layout entries are returned from a FSCTL_QUERY_FILE_LAYOUT request.
old-location: ifsk\query_file_layout_input.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["QUERY_FILE_LAYOUT_INPUT structure"]
ms.keywords: "*PQUERY_FILE_LAYOUT_INPUT, PQUERY_FILE_LAYOUT_INPUT, PQUERY_FILE_LAYOUT_INPUT structure pointer [Installable File System Drivers], QUERY_FILE_LAYOUT_FILTER_TYPE_CLUSTERS, QUERY_FILE_LAYOUT_FILTER_TYPE_FILEID, QUERY_FILE_LAYOUT_FILTER_TYPE_NONE, QUERY_FILE_LAYOUT_INCLUDE_EXTENTS, QUERY_FILE_LAYOUT_INCLUDE_EXTRA_INFO, QUERY_FILE_LAYOUT_INCLUDE_NAMES, QUERY_FILE_LAYOUT_INCLUDE_STREAMS, QUERY_FILE_LAYOUT_INCLUDE_STREAMS_WITH_NO_CLUSTERS_ALLOCATED, QUERY_FILE_LAYOUT_INPUT, QUERY_FILE_LAYOUT_INPUT structure [Installable File System Drivers], QUERY_FILE_LAYOUT_RESTART, _QUERY_FILE_LAYOUT_INPUT, ifsk.query_file_layout_input, ntifs/PQUERY_FILE_LAYOUT_INPUT, ntifs/QUERY_FILE_LAYOUT_INPUT"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.typenames: QUERY_FILE_LAYOUT_INPUT, *PQUERY_FILE_LAYOUT_INPUT
f1_keywords:
 - _QUERY_FILE_LAYOUT_INPUT
 - ntifs/_QUERY_FILE_LAYOUT_INPUT
 - PQUERY_FILE_LAYOUT_INPUT
 - ntifs/PQUERY_FILE_LAYOUT_INPUT
 - QUERY_FILE_LAYOUT_INPUT
 - ntifs/QUERY_FILE_LAYOUT_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntifs.h
api_name:
 - _QUERY_FILE_LAYOUT_INPUT
 - PQUERY_FILE_LAYOUT_INPUT
 - QUERY_FILE_LAYOUT_INPUT
---

# QUERY_FILE_LAYOUT_INPUT structure

## -description

The **QUERY_FILE_LAYOUT_INPUT** structure selects which file layout entries are returned from a [**FSCTL_QUERY_FILE_LAYOUT**](/windows-hardware/drivers/ifs/fsctl-query-file-layout) request.

## -struct-fields

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.FilterEntryCount

The number of filter entries in the **Filter** array.

### -field DUMMYUNIONNAME.NumberOfPairs

The original name of the field when there was only one type of filter. The union is simply to maintain code compatibility.

### -field Flags

Indicates which file layout entries are included in the query results. **Flags** is set to a valid combination of the following values.

| Value | Meaning |
| ----- | ------- |
| **QUERY_FILE_LAYOUT_INCLUDE_EXTENTS** | Stream extent entries are included in the query results. To use this flag, the **QUERY_FILE_LAYOUT_INCLUDE_STREAMS** flag must also be set. |
| **QUERY_FILE_LAYOUT_INCLUDE_EXTRA_INFO** | Extra file information name entries are included in the query results. |
| **QUERY_FILE_LAYOUT_INCLUDE_NAMES** | File name entries are included in the query results. |
| **QUERY_FILE_LAYOUT_INCLUDE_STREAMS** | File stream entries are included in the query results. |
| **QUERY_FILE_LAYOUT_RESTART** | Reset the file layout entry iterator to the beginning of the volume. |
| **QUERY_FILE_LAYOUT_INCLUDE_STREAMS_WITH_NO_CLUSTERS_ALLOCATED** | Include entries for resident streams and unallocated attributes. To use this flag, the **QUERY_FILE_LAYOUT_INCLUDE_STREAMS** flag must also be set. |

### -field FilterType

Specifies a filtering method to restrict returned layout information. Can be one of following values.

| Value | Meaning |
| ----- | ------- |
| **QUERY_FILE_LAYOUT_FILTER_TYPE_NONE** | Perform no filtering and return all information. When using this type, **NumberOfPairs** must be 0. |
| **QUERY_FILE_LAYOUT_FILTER_TYPE_CLUSTERS** | Restrict filter layout information to the ranges in **Filter.ClusterRanges**. |
| **QUERY_FILE_LAYOUT_FILTER_TYPE_FILEID** | Restrict filter layout information to the ranges in **Filter.FileReferenceRanges**. |

### -field Reserved

Reserved for system use.

### -field Filter

An array of filter structures used to select specific layout information. These contain either cluster or file reference ranges. The array length is specified by the **NumberOfPairs** member. Each range must be distinct and cannot overlap with any other range.

This member is ignored if **QUERY_FILE_LAYOUT_FILTER_TYPE_NONE** is specified in **FilterType**.

### -field Filter.ClusterRanges

Specifies a set of cluster ranges to filter layout information. The range structure has the following format.

``` C
typedef struct _CLUSTER_RANGE {
    LARGE_INTEGER    StartingCluster;
    LARGE_INTEGER    ClusterCount;
} CLUSTER_RANGE, *PCLUSTER_RANGE;
```

### -field Filter.FileReferenceRanges

Specifies a set of file reference ranges to filter layout information. Available starting in Windows 10 version 1809. The range structure has the following format.

``` C
typedef struct _FILE_REFERENCE_RANGE {
    LARGE_INTEGER    StartingFileReference;
    LARGE_INTEGER    EndingReferenceNumber;
} FILE_REFERENCE_RANGE, *PFILE_REFERENCE_RANGE;
```

### -field Filter.StorageReserveIds

Specifies a set of storage reserve IDs to filter layout information. The associated enumeration has the following format.

``` C
typedef enum _STORAGE_RESERVE_ID {

    StorageReserveIdNone = 0,
    StorageReserveIdHard,
    StorageReserveIdSoft,
    StorageReserveIdUpdateScratch,

    StorageReserveIdMax

} STORAGE_RESERVE_ID, *PSTORAGE_RESERVE_ID;
```

## -remarks

The **QUERY_FILE_LAYOUT_RESTART** flag is set on the first [**FSCTL_QUERY_FILE_LAYOUT**](/windows-hardware/drivers/ifs/fsctl-query-file-layout) request. If filter ranges are included in the request, they are cached when **QUERY_FILE_LAYOUT_RESTART** is set. Further requests will return layout file entries until the end of the volume or until filter ranges are exhausted.

If **QUERY_FILE_LAYOUT_RESTART** is set again for the same volume, the file layout position is reset to the beginning of the volume. Additionally, the filter ranges are re-cached and their  evaluation order is reset to the first range.

The file layout entries are returned in the output buffer following a [**QUERY_FILE_LAYOUT_OUTPUT**](ns-ntifs-_query_file_layout_output.md) structure.

When **FilterType** is **QUERY_FILE_LAYOUT_FILTER_TYPE_CLUSTERS**, the **ClusterRanges** member of the **Filter** union is used for range filtering. Otherwise, if **FilterType** is **QUERY_FILE_LAYOUT_FILTER_TYPE_FILEID**, the **FileReferenceRanges** member is used for range filtering.

## -see-also

[**FSCTL_QUERY_FILE_LAYOUT**](/windows-hardware/drivers/ifs/fsctl-query-file-layout)

[**QUERY_FILE_LAYOUT_OUTPUT**](ns-ntifs-_query_file_layout_output.md)
