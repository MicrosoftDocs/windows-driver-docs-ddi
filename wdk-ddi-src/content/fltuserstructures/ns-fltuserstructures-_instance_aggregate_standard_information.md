---
UID: NS:fltuserstructures._INSTANCE_AGGREGATE_STANDARD_INFORMATION
title: _INSTANCE_AGGREGATE_STANDARD_INFORMATION (fltuserstructures.h)
description: The caller-allocated INSTANCE_AGGREGATE_STANDARD_INFORMATION structure contains information for either a minifilter driver instance or a legacy filter driver.
old-location: ifsk\instance_aggregate_standard_information.htm
tech.root: ifsk
ms.assetid: 35311ee7-d023-4b04-b510-a949ab9a40ca
ms.date: 09/18/2019
keywords: ["INSTANCE_AGGREGATE_STANDARD_INFORMATION structure"]
ms.keywords: "*PINSTANCE_AGGREGATE_STANDARD_INFORMATION, FltSystemStructures_b1c8bf6f-d693-4f15-ad58-9e31d593464b.xml, INSTANCE_AGGREGATE_STANDARD_INFORMATION, INSTANCE_AGGREGATE_STANDARD_INFORMATION structure [Installable File System Drivers], PINSTANCE_AGGREGATE_STANDARD_INFORMATION, PINSTANCE_AGGREGATE_STANDARD_INFORMATION structure pointer [Installable File System Drivers], SUPPORTED_FS_FEATURES_OFFLOAD_READ, SUPPORTED_FS_FEATURES_OFFLOAD_WRITE, _INSTANCE_AGGREGATE_STANDARD_INFORMATION, fltuserstructures/INSTANCE_AGGREGATE_STANDARD_INFORMATION, fltuserstructures/PINSTANCE_AGGREGATE_STANDARD_INFORMATION, ifsk.instance_aggregate_standard_information"
req.header: fltuserstructures.h
req.include-header: FltUser.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows Vista.
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
req.typenames: INSTANCE_AGGREGATE_STANDARD_INFORMATION, *PINSTANCE_AGGREGATE_STANDARD_INFORMATION
f1_keywords:
 - _INSTANCE_AGGREGATE_STANDARD_INFORMATION
 - fltuserstructures/_INSTANCE_AGGREGATE_STANDARD_INFORMATION
 - PINSTANCE_AGGREGATE_STANDARD_INFORMATION
 - fltuserstructures/PINSTANCE_AGGREGATE_STANDARD_INFORMATION
 - INSTANCE_AGGREGATE_STANDARD_INFORMATION
 - fltuserstructures/INSTANCE_AGGREGATE_STANDARD_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fltuserstructures.h
api_name:
 - INSTANCE_AGGREGATE_STANDARD_INFORMATION
---

# _INSTANCE_AGGREGATE_STANDARD_INFORMATION structure


## -description

The caller-allocated INSTANCE_AGGREGATE_STANDARD_INFORMATION structure contains information for either a minifilter driver instance or a legacy filter driver.

## -struct-fields

### -field NextEntryOffset

Byte offset of the next INSTANCE_AGGREGATE_STANDARD_INFORMATION structure if multiple structures are present in a buffer. This member is zero if no other structures follow this one.

### -field Flags

Indicates whether the filter driver is a legacy filter driver or a minifilter driver.  This member must contain one of the following flags.

| Flag | Meaning |
| ---- | ------- |
| FLTFL_IASI_IS_MINIFILTER | The filter driver is a minifilter driver; use the **MiniFilter** portion of the union. |
| FLTFL_IASI_IS_LEGACYFILTER | The filter driver is a legacy filter driver; use the **LegacyFilter** portion of the union. |

### -field Type

Nested structure variable with the following members.

### -field Type.MiniFilter

### -field Type.MiniFilter.Flags

A bitmask of flags that describe attributes of the minifilter instance. The following are valid flag values.

| Flag | Meaning |
| ---- | ------- |
| FLTFL_IASIM_DETACHED_VOLUME | The volume is not currently attached to a storage stack. |

### -field Type.MiniFilter.FrameID

Zero-based index used to identify the filter manager frame that the minifilter instance is in.

### -field Type.MiniFilter.VolumeFileSystemType

Identifies the type of file system the minifilter instance is attached to.  The possible values for this member are listed in [FLT_FILESYSTEM_TYPE](./ne-fltuserstructures-_flt_filesystem_type.md).

### -field Type.MiniFilter.InstanceNameLength

Length, in bytes, of the minifilter instance name.

### -field Type.MiniFilter.InstanceNameBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode minifilter instance name string. This string is not NULL-terminated.

### -field Type.MiniFilter.AltitudeLength

Length, in bytes, of the minifilter instance altitude string.

### -field Type.MiniFilter.AltitudeBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode minifilter instance altitude string. This string is not NULL-terminated.

### -field Type.MiniFilter.VolumeNameLength

Length, in bytes, of the volume name of the volume that the minifilter instance is attached to.

### -field Type.MiniFilter.VolumeNameBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode volume name string for the volume that the minifilter instance is attached to. This string is not NULL-terminated.

### -field Type.MiniFilter.FilterNameLength

Length, in bytes, of the minifilter name of the minifilter from which the minifilter instance was derived.

### -field Type.MiniFilter.FilterNameBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode minifilter name string for the minifilter from which the minifilter instance was derived. This string is not NULL-terminated.

### -field Type.MiniFilter.SupportedFeatures

The supported feature flags for the filter. The supported features are a bitwise OR combination of the following flags.

| Value | Meaning |
| ----- | ------- |
| SUPPORTED_FS_FEATURES_OFFLOAD_READ (0x00000001) | The volume supports offloaded read operations. |
| SUPPORTED_FS_FEATURES_OFFLOAD_WRITE (0x00000002) | The volume supports offloaded write operations. |
| SUPPORTED_FS_FEATURES_QUERY_OPEN (0x00000004) | The volume supports query open operations. |

### -field Type.LegacyFilter

Nested structure variable with the following members.

### -field Type.LegacyFilter.Flags

A bitmask of flags that describe attributes of the legacy filter. The following are valid flag values.

| Flag | Meaning |
| ---- | ------- |
| FLTFL_IASIL_DETACHED_VOLUME | The volume is not currently attached to a storage stack. |

### -field Type.LegacyFilter.AltitudeLength

Length, in bytes, of the legacy filter altitude string.

### -field Type.LegacyFilter.AltitudeBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode legacy filter altitude string. This string is not NULL-terminated.

Starting with Windows Vista, altitudes are assigned to legacy filter drivers based on the driver's load order group. This ensures that minifilter drivers will layer properly above and below legacy filter drivers even if one or more of the filter drivers are loaded out-of-order.

### -field Type.LegacyFilter.VolumeNameLength

Length, in bytes, of the volume name of the volume that the legacy filter is attached to.

### -field Type.LegacyFilter.VolumeNameBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode volume name string for the volume that the legacy filter is attached to. This string is not NULL-terminated.

### -field Type.LegacyFilter.FilterNameLength

Length, in bytes, of the legacy filter name.

### -field Type.LegacyFilter.FilterNameBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode legacy filter name string. This string is not NULL-terminated.

### -field Type.LegacyFilter.SupportedFeatures

The supported feature flags for the filter.

The supported features are a bitwise OR combination of the following flags.

| Value | Meaning |
| ----- | ------- |
| SUPPORTED_FS_FEATURES_OFFLOAD_READ (0x00000001) | The volume supports offloaded read operations. |
| SUPPORTED_FS_FEATURES_OFFLOAD_WRITE (0x00000002) | The volume supports offloaded write operations. |

## -remarks

A structure of type INSTANCE_AGGREGATE_STANDARD_INFORMATION can be allocated from paged or nonpaged pool.  This structure is passed as a parameter to routines such as the following:

- [FilterInstanceFindFirst](/windows/win32/api/fltuser/nf-fltuser-filterinstancefindfirst)
- [FilterInstanceFindNext](/windows/win32/api/fltuser/nf-fltuser-filterinstancefindnext)
- [FilterInstanceGetInformation](/windows/win32/api/fltuser/nf-fltuser-filterinstancegetinformation)
- [FilterVolumeInstanceFindFirst](/windows/win32/api/fltuser/nf-fltuser-filtervolumeinstancefindfirst)
- [FilterVolumeInstanceFindNext](/windows/win32/api/fltuser/nf-fltuser-filtervolumeinstancefindnext)
- [FltEnumerateInstanceInformationByFilter](../fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyfilter.md)
- [FltEnumerateInstanceInformationByVolume](../fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyvolume.md)
- [FltGetInstanceInformation](../fltkernel/nf-fltkernel-fltgetinstanceinformation.md)

The INSTANCE_AGGREGATE_STANDARD_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the **NextEntryOffset** value in each entry falls on an 8-byte boundary.

## -see-also

[FilterInstanceFindFirst](/windows/win32/api/fltuser/nf-fltuser-filterinstancefindfirst)

[FilterInstanceFindNext](/windows/win32/api/fltuser/nf-fltuser-filterinstancefindnext)

[FilterInstanceGetInformation](/windows/win32/api/fltuser/nf-fltuser-filterinstancegetinformation)

[FilterVolumeInstanceFindFirst](/windows/win32/api/fltuser/nf-fltuser-filtervolumeinstancefindfirst)

[FilterVolumeInstanceFindNext](/windows/win32/api/fltuser/nf-fltuser-filtervolumeinstancefindnext)

[FltEnumerateInstanceInformationByFilter](../fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyfilter.md)

[FltEnumerateInstanceInformationByVolume](../fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyvolume.md)

[FltGetInstanceInformation](../fltkernel/nf-fltkernel-fltgetinstanceinformation.md)

[INSTANCE_BASIC_INFORMATION](./ns-fltuserstructures-_instance_basic_information.md)

[INSTANCE_FULL_INFORMATION](./ns-fltuserstructures-_instance_full_information.md)

[INSTANCE_PARTIAL_INFORMATION](./ns-fltuserstructures-_instance_partial_information.md)