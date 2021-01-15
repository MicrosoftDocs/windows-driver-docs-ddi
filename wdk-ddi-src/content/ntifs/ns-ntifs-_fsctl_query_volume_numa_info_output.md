---
UID: NS:ntifs._FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
title: _FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT (ntifs.h)
description: The FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT structure specifies the Non-Uniform Memory Architecture (NUMA) node the volume resides on.
old-location: ifsk\fsctl_query_volume_numa_info_output_.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT structure"]
ms.keywords: "*PFSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT, FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT, FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT , FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT structure [Installable File System Drivers], PFSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT, PFSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT structure pointer [Installable File System Drivers], _FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT, ifsk.fsctl_query_volume_numa_info_output_, ntifs/FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT, ntifs/PFSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT"
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT, *PFSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
f1_keywords:
 - _FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
 - ntifs/_FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
 - PFSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
 - ntifs/PFSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
 - FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
 - ntifs/FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntifs.h
api_name:
 - _FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
 - PFSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
 - FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT
---

# _FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT structure


## -description

The <b>FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT</b> structure specifies the Non-Uniform Memory Architecture (NUMA) node the volume resides on.

## -struct-fields

### -field NumaNode

Specifies the number of the NUMA node the volume resides on.

