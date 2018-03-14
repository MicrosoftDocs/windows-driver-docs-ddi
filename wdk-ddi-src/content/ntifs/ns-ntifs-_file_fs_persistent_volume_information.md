---
UID: NS:ntifs._FILE_FS_PERSISTENT_VOLUME_INFORMATION
title: "_FILE_FS_PERSISTENT_VOLUME_INFORMATION"
author: windows-driver-content
description: The FILE_FS_PERSISTENT_VOLUME_INFORMATION structure is used to control persistent settings for a file system volume. Persistent settings persist on a file system volume between reboots of the computer.
old-location: ifsk\file_fs_persistent_volume_information.htm
old-project: ifsk
ms.assetid: f1c7785e-e135-4060-8cf7-5c985b37ff83
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_FS_PERSISTENT_VOLUME_INFORMATION, FILE_FS_PERSISTENT_VOLUME_INFORMATION, FILE_FS_PERSISTENT_VOLUME_INFORMATION structure [Installable File System Drivers], PERSISTENT_VOLUME_STATE_BACKED_BY_WIM, PERSISTENT_VOLUME_STATE_CONTAINS_BACKING_WIM, PERSISTENT_VOLUME_STATE_GLOBAL_METADATA_NO_SEEK_PENALTY, PERSISTENT_VOLUME_STATE_LOCAL_METADATA_NO_SEEK_PENALTY, PERSISTENT_VOLUME_STATE_NO_HEAT_GATHERING, PERSISTENT_VOLUME_STATE_SHORT_NAME_CREATION_DISABLED, PERSISTENT_VOLUME_STATE_VOLUME_SCRUB_DISABLED, PFILE_FS_PERSISTENT_VOLUME_INFORMATION, PFILE_FS_PERSISTENT_VOLUME_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_PERSISTENT_VOLUME_INFORMATION, fileinformationstructures_81dcbc8f-6b7e-455e-b1b2-b99e6fd4084d.xml, ifsk.file_fs_persistent_volume_information, ntifs/FILE_FS_PERSISTENT_VOLUME_INFORMATION, ntifs/PFILE_FS_PERSISTENT_VOLUME_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 7.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FILE_FS_PERSISTENT_VOLUME_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_FS_PERSISTENT_VOLUME_INFORMATION, *PFILE_FS_PERSISTENT_VOLUME_INFORMATION
---

# _FILE_FS_PERSISTENT_VOLUME_INFORMATION structure


## -description


The <b>FILE_FS_PERSISTENT_VOLUME_INFORMATION</b> structure is used to control persistent settings for a file system volume. Persistent settings persist on a file system volume between reboots of the computer. 


## -syntax


````
typedef struct _FILE_FS_PERSISTENT_VOLUME_INFORMATION {
  ULONG VolumeFlags;
  ULONG FlagMask;
  ULONG Version;
  ULONG Reserved;
} FILE_FS_PERSISTENT_VOLUME_INFORMATION, *PFILE_FS_PERSISTENT_VOLUME_INFORMATION;
````


## -struct-fields




### -field VolumeFlags

The persistent state settings for a file system volume. This value is a bitwise OR combination of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PERSISTENT_VOLUME_STATE_SHORT_NAME_CREATION_DISABLED"></a><a id="persistent_volume_state_short_name_creation_disabled"></a><dl>
<dt><b>PERSISTENT_VOLUME_STATE_SHORT_NAME_CREATION_DISABLED</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
A 0 for this bit indicates that the creation of 8.3 short names is enabled, and a 1 indicates that short name creation is disabled. 8.3 short file names have at most eight characters, followed by a period "." and a file name extension of at most three characters.

</td>
</tr>
<tr>
<td width="40%"><a id="PERSISTENT_VOLUME_STATE_VOLUME_SCRUB_DISABLED"></a><a id="persistent_volume_state_volume_scrub_disabled"></a><dl>
<dt><b>PERSISTENT_VOLUME_STATE_VOLUME_SCRUB_DISABLED</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
When set, this flag indicates that the volume scrub is disabled for the volume.

This flag is valid starting with Windows 8.

</td>
</tr>
<tr>
<td width="40%"><a id="PERSISTENT_VOLUME_STATE_GLOBAL_METADATA_NO_SEEK_PENALTY"></a><a id="persistent_volume_state_global_metadata_no_seek_penalty"></a><dl>
<dt><b>PERSISTENT_VOLUME_STATE_GLOBAL_METADATA_NO_SEEK_PENALTY</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
Global no seek penalty is enabled for a tiered volume.

This flag is valid starting with Windows 8.1.

</td>
</tr>
<tr>
<td width="40%"><a id="PERSISTENT_VOLUME_STATE_LOCAL_METADATA_NO_SEEK_PENALTY"></a><a id="persistent_volume_state_local_metadata_no_seek_penalty"></a><dl>
<dt><b>PERSISTENT_VOLUME_STATE_LOCAL_METADATA_NO_SEEK_PENALTY</b></dt>
<dt>0x00000008</dt>
</dl>
</td>
<td width="60%">
Local no seek penalty is enabled for a tiered volume.

This flag is valid starting with Windows 8.1.

</td>
</tr>
<tr>
<td width="40%"><a id="PERSISTENT_VOLUME_STATE_NO_HEAT_GATHERING"></a><a id="persistent_volume_state_no_heat_gathering"></a><dl>
<dt><b>PERSISTENT_VOLUME_STATE_NO_HEAT_GATHERING</b></dt>
<dt>0x00000010</dt>
</dl>
</td>
<td width="60%">
When set, heat gathering is not enabled for the tiered volume.

This flag is valid starting with Windows 8.1.

</td>
</tr>
<tr>
<td width="40%"><a id="PERSISTENT_VOLUME_STATE_CONTAINS_BACKING_WIM"></a><a id="persistent_volume_state_contains_backing_wim"></a><dl>
<dt><b>PERSISTENT_VOLUME_STATE_CONTAINS_BACKING_WIM</b></dt>
<dt>0x00000020</dt>
</dl>
</td>
<td width="60%">
Indicates that this volume is backing the system volume with files  from a Windows Image Format (WIM) file.

This flag is valid starting with Windows 8.1 Update.

</td>
</tr>
<tr>
<td width="40%"><a id="PERSISTENT_VOLUME_STATE_BACKED_BY_WIM"></a><a id="persistent_volume_state_backed_by_wim"></a><dl>
<dt><b>PERSISTENT_VOLUME_STATE_BACKED_BY_WIM</b></dt>
<dt>0x00000040</dt>
</dl>
</td>
<td width="60%">
Indicates that this volume is dependent on another volume to provide system critical boot files. The other  volume contains a WIM file that backs the files on this volume. This flag is read only.

This flag is valid starting with Windows 8.1 Update.

</td>
</tr>
</table>
 


### -field FlagMask

A mask value for the valid flags that can appear in <b>VolumeFlags</b>. This is a bitwise OR combination of the desired flags described for <b>VolumeFlags</b>.


### -field Version

The version number of this structure. Set to 1.


### -field Reserved

Reserved. Set to 0;


## -remarks



The <b>FILE_FS_PERSISTENT_VOLUME_INFORMATION</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545564">FSCTL_SET_PERSISTENT_VOLUME_STATE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545496">FSCTL_QUERY_PERSISTENT_VOLUME_STATE</a> control codes.

To query the state flags, <b>FlagMask</b> is set to a combination of flags to check for. For example, if the only the seek penalty flags are of interest, <b>FlagMask</b> = PERSISTENT_VOLUME_STATE_GLOBAL_METADATA_NO_SEEK_PENALTY | PERSISTENT_VOLUME_STATE_LOCAL_METADATA_NO_SEEK_PENALTY. Also, if only short name support is queried, then set <b>FlagMask</b> = PERSISTENT_VOLUME_STATE_SHORT_NAME_CREATION_DISABLED.

When setting or clearing the persistent volume state flags, using <a href="https://msdn.microsoft.com/library/windows/hardware/ff545564">FSCTL_SET_PERSISTENT_VOLUME_STATE</a>, <b>FlagMask</b> is set to all of the flags in <b>VolumeFlags</b> that will be affected for the volume. <b>VolumeFlags</b> contains the actual persistent state flags to set for the volume. The following example shows how to set the members of <b>FILE_FS_PERSISTENT_VOLUME_INFORMATION</b> to enable short name creation for a volume.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>IO_STATUS_BLOCK IoStatus;
FILE_FS_PERSISTENT_VOLUME_INFORMATION PersistVolInfo;
NTSTATUS status;

PersistVolInfo.VolumeFlags = 0;    // enable shortname creation on this volume
PersistVolInfo.FlagMask    = PERSISTENT_VOLUME_STATE_SHORT_NAME_CREATION_DISABLED;
PersistVolInfo.Version     = 1;
PersistVolInfo.Reserved    = 0;

// issue the request to the file system to set the enable state
//
status = ZwFsControlFile( VolumeHandle,
                          NULL,
                          NULL,
                          NULL,
                          &amp;IoStatus,
                          FSCTL_SET_PERSISTENT_VOLUME_STATE,
                          &amp;PersistVolInfo,
                          sizeof(FILE_FS_PERSISTENT_VOLUME_INFORMATION),
                          NULL,
                          0 );</pre>
</td>
</tr>
</table></span></div>
The <b>Version</b> member must be set to the current version of 1 for both a query and  a set  request.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545496">FSCTL_QUERY_PERSISTENT_VOLUME_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545564">FSCTL_SET_PERSISTENT_VOLUME_STATE</a>



 

 


