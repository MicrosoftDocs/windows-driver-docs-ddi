---
UID: NF:ntifs.FsRtlInitializeExtraCreateParameterList
title: FsRtlInitializeExtraCreateParameterList function (ntifs.h)
description: The FsRtlInitializeExtraCreateParameterList routine initializes an extra create parameter (ECP) context structure list.
old-location: ifsk\fsrtlinitializeextracreateparameterlist.htm
tech.root: ifsk
ms.assetid: 79e56363-1098-42bb-8e6a-c4b4c76e7e7c
ms.date: 04/16/2018
keywords: ["FsRtlInitializeExtraCreateParameterList function"]
ms.keywords: FsRtlInitializeExtraCreateParameterList, FsRtlInitializeExtraCreateParameterList routine [Installable File System Drivers], fsrtlref_785d3f11-f568-491e-9cdb-abba70ae3eeb.xml, ifsk.fsrtlinitializeextracreateparameterlist, ntifs/FsRtlInitializeExtraCreateParameterList
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlInitializeExtraCreateParameterList routine is available starting with Windows 7.
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
 - FsRtlInitializeExtraCreateParameterList
 - ntifs/FsRtlInitializeExtraCreateParameterList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlInitializeExtraCreateParameterList
---

# FsRtlInitializeExtraCreateParameterList function


## -description

The <b>FsRtlInitializeExtraCreateParameterList</b> routine initializes an extra create parameter (ECP) context structure list.

## -parameters

### -param EcpList 

[in, out]
Pointer to the <a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a> structure to initialize.

## -returns

<b>FsRtlInitializeExtraCreateParameterList</b> returns STATUS_SUCCESS if it successfully initialized the given <a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a> structure, and returns an error if it did not.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>