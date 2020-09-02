---
UID: NF:dbgeng.IDebugPlmClient3.EnablePlmPackageDebugWide
title: IDebugPlmClient3::EnablePlmPackageDebugWide (dbgeng.h)
description: Enables a Process Lifecycle Management (PLM) package debug.
old-location: debugger\idebugplmclient3_enableplmpackagedebugwide.htm
tech.root: debugger
ms.assetid: 6373B8BD-264D-4D03-9FE9-F87E45D617EE
ms.date: 05/03/2018
keywords: ["IDebugPlmClient3::EnablePlmPackageDebugWide"]
ms.keywords: EnablePlmPackageDebugWide, EnablePlmPackageDebugWide method [Windows Debugging], EnablePlmPackageDebugWide method [Windows Debugging],IDebugPlmClient3 interface, IDebugPlmClient3 interface [Windows Debugging],EnablePlmPackageDebugWide method, IDebugPlmClient3.EnablePlmPackageDebugWide, IDebugPlmClient3::EnablePlmPackageDebugWide, dbgeng/IDebugPlmClient3::EnablePlmPackageDebugWide, debugger.idebugplmclient3_enableplmpackagedebugwide
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
 - IDebugPlmClient3::EnablePlmPackageDebugWide
 - dbgeng/IDebugPlmClient3::EnablePlmPackageDebugWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugPlmClient3.EnablePlmPackageDebugWide
---

# IDebugPlmClient3::EnablePlmPackageDebugWide


## -description

Enables a Process Lifecycle Management (PLM) package debug.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugplmclient3">IDebugPlmClient3</a>

