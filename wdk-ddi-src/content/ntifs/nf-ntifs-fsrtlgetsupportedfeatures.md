---
UID: NF:ntifs.FsRtlGetSupportedFeatures
title: FsRtlGetSupportedFeatures function (ntifs.h)
description: The FsRtlGetSupportedFeatures routine returns the supported features of a volume attached to the specified device object.
old-location: ifsk\fsrtlgetsupportedfeatures.htm
tech.root: ifsk
ms.date: 05/29/2020
keywords: ["FsRtlGetSupportedFeatures function"]
ms.keywords: FsRtlGetSupportedFeatures, FsRtlGetSupportedFeatures routine [Installable File System Drivers], SUPPORTED_FS_FEATURES_OFFLOAD_READ, SUPPORTED_FS_FEATURES_OFFLOAD_WRITE, ifsk.fsrtlgetsupportedfeatures, ntifs/FsRtlGetSupportedFeatures
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlGetSupportedFeatures
 - ntifs/FsRtlGetSupportedFeatures
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlGetSupportedFeatures
---

# FsRtlGetSupportedFeatures function


## -description

The **FsRtlGetSupportedFeatures** routine returns the supported features of a volume attached to the specified device object.

## -parameters

### -param DeviceObject 

[in]
The target device object attached to a volume.

### -param SupportedFeatures 

[out]
A pointer to a caller-supplied **ULONG** value. On return, this value contains the supported feature flags for the attached volume.

The supported features are a bitwise OR combination of the following flags.

| Value | Meaning |
| ----- | ------- |
| **SUPPORTED_FS_FEATURES_OFFLOAD_READ**  0x00000001 | The volume supports offloaded read operations.  |
| **SUPPORTED_FS_FEATURES_OFFLOAD_WRITE** 0x00000002 | The volume supports offloaded write operations. |
| **SUPPORTED_FS_FEATURES_QUERY_OPEN**    0x00000004 | The volume supports query open operations. |

## -returns

**FsRtlGetSupportedFeatures** returns **STATUS_SUCCESS** if the supported features for the volume attached to *DeviceObject* are returned successfully. Otherwise, an **NTSTATUS** value such as one of the following is returned.

| Return code | Description |
| ----------- | ----------- |
| **STATUS_FLT_VOLUME_NOT_FOUND** | No volume is found for *DeviceObject*. |
| **STATUS_FLT_INTERNAL_ERROR**   | The device object specified by *DeviceObject* is not in a file system device stack. |

## -remarks

Filter Manager looks at the supported features, specified by a minifilter's **SupportedFeatures** Registry value, for every minifilter attached to the volume. Every attached minifilter must support a specific feature in order for that feature bit to be set. The **SupportedFeatures** value does not apply to file systems.

