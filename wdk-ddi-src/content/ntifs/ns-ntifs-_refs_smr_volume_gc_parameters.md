---
UID: NS:ntifs._REFS_SMR_VOLUME_GC_PARAMETERS
title: _REFS_SMR_VOLUME_GC_PARAMETERS (ntifs.h)
description: The REFS_SMR_VOLUME_GC_PARAMETERS structure.
old-location: ifsk\refs_smr_volume_gc_parameters.htm
tech.root: ifsk
ms.assetid: 78C8FFFE-8A80-4C92-B822-5C6675E2BC18
ms.date: 04/16/2018
keywords: ["REFS_SMR_VOLUME_GC_PARAMETERS structure"]
ms.keywords: "*PREFS_SMR_VOLUME_GC_PARAMETERS, PREFS_SMR_VOLUME_GC_PARAMETERS, PREFS_SMR_VOLUME_GC_PARAMETERS structure pointer [Installable File System Drivers], REFS_SMR_VOLUME_GC_PARAMETERS, REFS_SMR_VOLUME_GC_PARAMETERS structure [Installable File System Drivers], _REFS_SMR_VOLUME_GC_PARAMETERS, ifsk.refs_smr_volume_gc_parameters, ntifs/PREFS_SMR_VOLUME_GC_PARAMETERS, ntifs/REFS_SMR_VOLUME_GC_PARAMETERS"
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
targetos: Windows
req.typenames: REFS_SMR_VOLUME_GC_PARAMETERS, *PREFS_SMR_VOLUME_GC_PARAMETERS
f1_keywords:
 - _REFS_SMR_VOLUME_GC_PARAMETERS
 - ntifs/_REFS_SMR_VOLUME_GC_PARAMETERS
 - PREFS_SMR_VOLUME_GC_PARAMETERS
 - ntifs/PREFS_SMR_VOLUME_GC_PARAMETERS
 - REFS_SMR_VOLUME_GC_PARAMETERS
 - ntifs/REFS_SMR_VOLUME_GC_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntifs.h
api_name:
 - REFS_SMR_VOLUME_GC_PARAMETERS
---

# _REFS_SMR_VOLUME_GC_PARAMETERS structure


## -description

The <b>REFS_SMR_VOLUME_GC_PARAMETERS</b> structure is used as the input structure for <a href="/windows-hardware/drivers/ifs/fsctl-set-refs-smr-volume-gc-parameters">FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS</a>.

## -struct-fields

### -field Version

Specifies the current version of <b>REFS_SMR_VOLUME_GC_PARAMETERS</b>. Version is currently ignored but should be set to <b>REFS_SMR_VOLUME_GC_PARAMETERS_VERSION_V1</b>.

### -field Flags

Specifies the flags. Flags is currently ignored.

### -field Action

Specifies the garbage collection action.

### -field Method

Specifies the garbage collection method or strategy. Currently only <b>MsSmrGcMethodCompaction</b> is allowed.

### -field IoGranularity

Specifies the volume's granularity. <b>IoGranularity</b> is a multiple of the cluster size up to the Shingled Magnetic Recording (SMR) band size (256 MB).  Zero or non-multiple of cluster size will result in a <b>STATUS_INVALID_PARAMETERS</b> status.

### -field CompressionFormat

Reserved for future use.

### -field Unused

Reserved for future use.

## -see-also

<a href="/windows-hardware/drivers/ifs/fsctl-set-refs-smr-volume-gc-parameters">FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS</a>