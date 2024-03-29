---
UID: NF:dbgeng.IDebugPlmClient3.ResumePlmPackageWide
title: IDebugPlmClient3::ResumePlmPackageWide (dbgeng.h)
description: Resumes a Process Lifecycle Management (PLM) package.
old-location: debugger\idebugplmclient3_resumeplmpackagewide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugPlmClient3::ResumePlmPackageWide"]
ms.keywords: IDebugPlmClient3 interface [Windows Debugging],ResumePlmPackageWide method, IDebugPlmClient3.ResumePlmPackageWide, IDebugPlmClient3::ResumePlmPackageWide, ResumePlmPackageWide, ResumePlmPackageWide method [Windows Debugging], ResumePlmPackageWide method [Windows Debugging],IDebugPlmClient3 interface, dbgeng/IDebugPlmClient3::ResumePlmPackageWide, debugger.idebugplmclient3_resumeplmpackagewide
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.typenames: 
f1_keywords:
 - IDebugPlmClient3::ResumePlmPackageWide
 - dbgeng/IDebugPlmClient3::ResumePlmPackageWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugPlmClient3::ResumePlmPackageWide
---

# IDebugPlmClient3::ResumePlmPackageWide


## -description

Resumes a Process Lifecycle Management (PLM) package.

## -parameters

### -param Server [in]


The server of the package.

### -param PackageFullName [in]


A pointer to the package name.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugplmclient3">IDebugPlmClient3</a>

