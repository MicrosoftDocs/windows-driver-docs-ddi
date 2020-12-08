---
UID: NF:dbgeng.IDebugPlmClient3.DisablePlmPackageDebugWide
title: IDebugPlmClient3::DisablePlmPackageDebugWide (dbgeng.h)
description: Disables a Process Lifecycle Management (PLM) package debug.
old-location: debugger\idebugplmclient3_disableplmpackagedebugwide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugPlmClient3::DisablePlmPackageDebugWide"]
ms.keywords: DisablePlmPackageDebugWide, DisablePlmPackageDebugWide method [Windows Debugging], DisablePlmPackageDebugWide method [Windows Debugging],IDebugPlmClient3 interface, IDebugPlmClient3 interface [Windows Debugging],DisablePlmPackageDebugWide method, IDebugPlmClient3.DisablePlmPackageDebugWide, IDebugPlmClient3::DisablePlmPackageDebugWide, dbgeng/IDebugPlmClient3::DisablePlmPackageDebugWide, debugger.idebugplmclient3_disableplmpackagedebugwide
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
 - IDebugPlmClient3::DisablePlmPackageDebugWide
 - dbgeng/IDebugPlmClient3::DisablePlmPackageDebugWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugPlmClient3.DisablePlmPackageDebugWide
---

# IDebugPlmClient3::DisablePlmPackageDebugWide


## -description

Disables a Process Lifecycle Management (PLM) package debug.

## -parameters

### -param Server 

[in]
The server of the package.

### -param PackageFullName 

[in]
A pointer to the package name.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugplmclient3">IDebugPlmClient3</a>
