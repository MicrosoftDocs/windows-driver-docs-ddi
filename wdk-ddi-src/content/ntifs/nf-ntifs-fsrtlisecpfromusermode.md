---
UID: NF:ntifs.FsRtlIsEcpFromUserMode
title: FsRtlIsEcpFromUserMode function (ntifs.h)
description: The FsRtlIsEcpFromUserMode routine determines whether an extra create parameter (ECP) context structure originated from user mode.
old-location: ifsk\fsrtlisecpfromusermode.htm
tech.root: ifsk
ms.assetid: cdc5d6a3-637e-4f0e-bc94-25bfe5763695
ms.date: 04/16/2018
keywords: ["FsRtlIsEcpFromUserMode function"]
ms.keywords: FsRtlIsEcpFromUserMode, FsRtlIsEcpFromUserMode routine [Installable File System Drivers], fsrtlref_14f09529-adf9-4113-bff4-5183ade20059.xml, ifsk.fsrtlisecpfromusermode, ntifs/FsRtlIsEcpFromUserMode
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: FsRtlIsEcpFromUserMode is available starting with Windows Vista.
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
 - FsRtlIsEcpFromUserMode
 - ntifs/FsRtlIsEcpFromUserMode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIsEcpFromUserMode
---

# FsRtlIsEcpFromUserMode function


## -description

The <b>FsRtlIsEcpFromUserMode</b> routine determines whether an extra create parameter (ECP) context structure originated from user mode.

## -parameters

### -param EcpContext 

[in]
Pointer to the ECP context structure to test.

## -returns

<b>FsRtlIsEcpFromUserMode</b> returns <b>TRUE</b> if the ECP context structure originated in user mode and <b>FALSE</b> if the ECP context structure originated in kernel mode.

