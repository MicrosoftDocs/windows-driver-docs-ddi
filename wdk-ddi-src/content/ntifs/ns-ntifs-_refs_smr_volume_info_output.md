---
UID: NS:ntifs._REFS_SMR_VOLUME_INFO_OUTPUT
title: "_REFS_SMR_VOLUME_INFO_OUTPUT"
author: windows-driver-content
description: The REFS_SMR_VOLUME_INFO_OUTPUT structure describes a Shingled Magnetic Recording (SMR) volume's current state on space and garbage collection activities.
old-location: ifsk\refs_smr_volume_info_output.htm
old-project: ifsk
ms.assetid: 0DCBAF5F-AEBC-4C4B-9DBD-F7A6FD6C7712
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PREFS_SMR_VOLUME_INFO_OUTPUT structure pointer [Installable File System Drivers], *PREFS_SMR_VOLUME_INFO_OUTPUT, ntifs/REFS_SMR_VOLUME_INFO_OUTPUT, _REFS_SMR_VOLUME_INFO_OUTPUT, ifsk.refs_smr_volume_info_output, REFS_SMR_VOLUME_INFO_OUTPUT, REFS_SMR_VOLUME_INFO_OUTPUT structure [Installable File System Drivers], ntifs/PREFS_SMR_VOLUME_INFO_OUTPUT, PREFS_SMR_VOLUME_INFO_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntifs.h
apiname:
-	REFS_SMR_VOLUME_INFO_OUTPUT
product: Windows
targetos: Windows
req.typenames: REFS_SMR_VOLUME_INFO_OUTPUT, *PREFS_SMR_VOLUME_INFO_OUTPUT
---

# _REFS_SMR_VOLUME_INFO_OUTPUT structure


## -description


The <b>REFS_SMR_VOLUME_INFO_OUTPUT</b> structure describes a Shingled Magnetic Recording (SMR) volume's  current  state on space and garbage collection activities.


## -syntax


````
typedef struct _REFS_SMR_VOLUME_INFO_OUTPUT {
  ULONG                    Version;
  ULONG                    Flags;
  LARGE_INTEGER            SizeOfRandomlyWritableTier;
  LARGE_INTEGER            FreeSpaceInRandomlyWritableTier;
  LARGE_INTEGER            SizeofSMRTier;
  LARGE_INTEGER             FreeSpaceInSMRTier;
  LARGE_INTEGER            UsableFreeSpaceInSMRTier;
  REFS_SMR_VOLUME_GC_STATE VolumeGcState;
  NTSTATUS                 VolumeGcLastStatus;
  ULONGLONG                Unused[7];
} REFS_SMR_VOLUME_INFO_OUTPUT, *PREFS_SMR_VOLUME_INFO_OUTPUT;
````


## -struct-fields




### -field Version

Currently ignored.  Will be set to zero for now.  


### -field Flags

Currently ignored. Will be set to zero for now.


### -field SizeOfRandomlyWritableTier

Specifies the total size of the randomly writable tier.


### -field FreeSpaceInRandomlyWritableTier

Specifies the free space within the randomly writable tier.


### -field SizeofSMRTier

Specifies the total size of the Shingled Magnetic Recording (SMR) tier.


### -field FreeSpaceInSMRTier

Specifies the free space the Shingled Magnetic Recording (SMR) tier.


### -field UsableFreeSpaceInSMRTier

Specifies the usable space the Shingled Magnetic Recording (SMR) tier.


### -field VolumeGcState

Specifies the current state of the garbage collector.


### -field VolumeGcLastStatus

Specifies the status of the last garbage collection using the specified method in <a href="..\ntifs\ne-ntifs-_refs_smr_volume_gc_method.md">REFS_SMR_VOLUME_GC_METHOD</a>.


### -field Unused

Reserved for future use.

