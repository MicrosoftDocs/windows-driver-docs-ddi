---
UID: NS:fltuserstructures._INSTANCE_AGGREGATE_STANDARD_INFORMATION
title: "_INSTANCE_AGGREGATE_STANDARD_INFORMATION"
author: windows-driver-content
description: The caller-allocated INSTANCE_AGGREGATE_STANDARD_INFORMATION structure contains information for either a minifilter driver instance or a legacy filter driver.
old-location: ifsk\instance_aggregate_standard_information.htm
old-project: ifsk
ms.assetid: 35311ee7-d023-4b04-b510-a949ab9a40ca
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PINSTANCE_AGGREGATE_STANDARD_INFORMATION, FltSystemStructures_b1c8bf6f-d693-4f15-ad58-9e31d593464b.xml, INSTANCE_AGGREGATE_STANDARD_INFORMATION, INSTANCE_AGGREGATE_STANDARD_INFORMATION structure [Installable File System Drivers], PINSTANCE_AGGREGATE_STANDARD_INFORMATION, PINSTANCE_AGGREGATE_STANDARD_INFORMATION structure pointer [Installable File System Drivers], SUPPORTED_FS_FEATURES_OFFLOAD_READ, SUPPORTED_FS_FEATURES_OFFLOAD_WRITE, _INSTANCE_AGGREGATE_STANDARD_INFORMATION, fltuserstructures/INSTANCE_AGGREGATE_STANDARD_INFORMATION, fltuserstructures/PINSTANCE_AGGREGATE_STANDARD_INFORMATION, ifsk.instance_aggregate_standard_information"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltuserstructures.h
api_name:
-	INSTANCE_AGGREGATE_STANDARD_INFORMATION
product: Windows
targetos: Windows
req.typenames: INSTANCE_AGGREGATE_STANDARD_INFORMATION, *PINSTANCE_AGGREGATE_STANDARD_INFORMATION
---

# _INSTANCE_AGGREGATE_STANDARD_INFORMATION structure


## -description


The caller-allocated INSTANCE_AGGREGATE_STANDARD_INFORMATION structure contains information for either a minifilter driver instance or a legacy filter driver.


## -struct-fields




### -field NextEntryOffset

Byte offset of the next INSTANCE_AGGREGATE_STANDARD_INFORMATION structure if multiple structures are present in a buffer. This member is zero if no other structures follow this one.


### -field Flags

Indicates whether the filter driver is a legacy filter driver or a minifilter driver.  This member must contain one of the following flags.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLTFL_IASI_IS_MINIFILTER

</td>
<td>
The filter driver is a minifilter driver - use the <b>MiniFilter</b> portion of the union.

</td>
</tr>
<tr>
<td>
FLTFL_IASI_IS_LEGACYFILTER

</td>
<td>
The filter driver is a legacy filter driver - use the <b>LegacyFilter</b> portion of the union.

</td>
</tr>
</table>
 


### -field Type


### -field Type.MiniFilter

Nested structure variable with the following members.


### -field Type.MiniFilter.Flags

A bitmask of flags that describe attributes of the minifilter instance. The following are valid flag values.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>FLTFL_IASIM_DETACHED_VOLUME</td>
<td>The volume is not currently attached to a storage stack.</td>
</tr>
</table>
 


### -field Type.MiniFilter.FrameID

Zero-based index used to identify the filter manager frame that the minifilter instance is in. 


### -field Type.MiniFilter.VolumeFileSystemType

Identifies the type of file system the minifilter instance is attached to.  The possible values for this member are listed in <a href="https://msdn.microsoft.com/library/windows/hardware/ff625876">FLT_FILESYSTEM_TYPE</a>.


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

The supported feature flags for the filter.


The supported features are a bitwise OR combination of the following flags.



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="SUPPORTED_FS_FEATURES_OFFLOAD_READ"></a><a id="supported_fs_features_offload_read"></a><dl>
<dt><b>SUPPORTED_FS_FEATURES_OFFLOAD_READ</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
The volume supports offloaded read operations

</td>
</tr>
<tr>
<td width="40%"><a id="SUPPORTED_FS_FEATURES_OFFLOAD_WRITE"></a><a id="supported_fs_features_offload_write"></a><dl>
<dt><b>SUPPORTED_FS_FEATURES_OFFLOAD_WRITE</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
The volume supports offloaded write operations

</td>
</tr>
</table>
 


### -field Type.LegacyFilter


       Nested structure variable with the following members.
       
      


### -field Type.LegacyFilter.Flags

A bitmask of flags that describe attributes of the legacy filter. The following are valid flag values.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>FLTFL_IASIL_DETACHED_VOLUME</td>
<td>The volume is not currently attached to a storage stack.</td>
</tr>
</table>
 


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



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="SUPPORTED_FS_FEATURES_OFFLOAD_READ"></a><a id="supported_fs_features_offload_read"></a><dl>
<dt><b>SUPPORTED_FS_FEATURES_OFFLOAD_READ</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
The volume supports offloaded read operations

</td>
</tr>
<tr>
<td width="40%"><a id="SUPPORTED_FS_FEATURES_OFFLOAD_WRITE"></a><a id="supported_fs_features_offload_write"></a><dl>
<dt><b>SUPPORTED_FS_FEATURES_OFFLOAD_WRITE</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
The volume supports offloaded write operations

</td>
</tr>
</table>
 


## -remarks



A structure of type INSTANCE_AGGREGATE_STANDARD_INFORMATION can be allocated from paged or nonpaged pool.  This structure is passed as a parameter to routines such as the following:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540541">FilterInstanceFindFirst</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541493">FilterInstanceFindNext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541499">FilterInstanceGetInformation</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541541">FilterVolumeInstanceFindFirst</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541551">FilterVolumeInstanceFindNext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542071">FltEnumerateInstanceInformationByFilter</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543062">FltGetInstanceInformation</a>


</li>
</ul>
The INSTANCE_AGGREGATE_STANDARD_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry falls on an 8-byte boundary.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540541">FilterInstanceFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541493">FilterInstanceFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541499">FilterInstanceGetInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541541">FilterVolumeInstanceFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541551">FilterVolumeInstanceFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542071">FltEnumerateInstanceInformationByFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542082">FltEnumerateInstanceInformationByVolume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543062">FltGetInstanceInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548176">INSTANCE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548185">INSTANCE_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548190">INSTANCE_PARTIAL_INFORMATION</a>
 

 

