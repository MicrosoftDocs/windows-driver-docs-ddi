---
UID: NF:ntifs.FsRtlGetSupportedFeatures
title: FsRtlGetSupportedFeatures function
author: windows-driver-content
description: The FsRtlGetSupportedFeatures routine returns the supported features of a volume attached to the specified device object.
old-location: ifsk\fsrtlgetsupportedfeatures.htm
old-project: ifsk
ms.assetid: 24852B9A-5156-41BB-87F9-81B147A85AC2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlGetSupportedFeatures, FsRtlGetSupportedFeatures routine [Installable File System Drivers], SUPPORTED_FS_FEATURES_OFFLOAD_READ, SUPPORTED_FS_FEATURES_OFFLOAD_WRITE, ifsk.fsrtlgetsupportedfeatures, ntifs/FsRtlGetSupportedFeatures
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlGetSupportedFeatures
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlGetSupportedFeatures function


## -description


The <b>FsRtlGetSupportedFeatures</b> routine returns the supported features of a volume attached to the specified device object.


## -parameters




### -param DeviceObject [in]

The target device object attached to a volume.


### -param SupportedFeatures [out]

A pointer to a caller supplied <b>ULONG</b> value. On return, this value contains the supported feature flags for the attached volume.


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
The volume supports offloaded read operations.

</td>
</tr>
<tr>
<td width="40%"><a id="SUPPORTED_FS_FEATURES_OFFLOAD_WRITE"></a><a id="supported_fs_features_offload_write"></a><dl>
<dt><b>SUPPORTED_FS_FEATURES_OFFLOAD_WRITE</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
The volume supports offloaded write operations.

</td>
</tr>
</table>
 


## -returns



<b>FsRtlGetSupportedFeatures</b> returns <b>STATUS_SUCCESS</b> if the supported features for the volume attached to <i>DeviceObject</i> are returned successfully. Otherwise, one of the following <b>NTSTATUS</b> values is returned.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_VOLUME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No volume is found for <i>DeviceObject</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The device object specified by <i>DeviceObject</i> is not in a file system device stack.

</td>
</tr>
</table>
 



