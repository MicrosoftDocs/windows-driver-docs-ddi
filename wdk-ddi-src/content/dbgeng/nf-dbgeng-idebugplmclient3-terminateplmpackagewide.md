---
UID: NF:dbgeng.IDebugPlmClient3.TerminatePlmPackageWide
title: IDebugPlmClient3::TerminatePlmPackageWide (dbgeng.h)
description: Ends a Process Lifecycle Management (PLM) package.
old-location: debugger\idebugplmclient3_terminateplmpackagewide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugPlmClient3::TerminatePlmPackageWide"]
ms.keywords: IDebugPlmClient3 interface [Windows Debugging],TerminatePlmPackageWide method, IDebugPlmClient3.TerminatePlmPackageWide, IDebugPlmClient3::TerminatePlmPackageWide, TerminatePlmPackageWide, TerminatePlmPackageWide method [Windows Debugging], TerminatePlmPackageWide method [Windows Debugging],IDebugPlmClient3 interface, dbgeng/IDebugPlmClient3::TerminatePlmPackageWide, debugger.idebugplmclient3_terminateplmpackagewide
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
 - IDebugPlmClient3::TerminatePlmPackageWide
 - dbgeng/IDebugPlmClient3::TerminatePlmPackageWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugPlmClient3::TerminatePlmPackageWide
---

# IDebugPlmClient3::TerminatePlmPackageWide


## -description

Ends a Process Lifecycle Management (PLM) package.

## -parameters

### -param Server [in]


The server of the package.

### -param PackageFullName [in]


A pointer to the package name.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugplmclient3">IDebugPlmClient3</a>

