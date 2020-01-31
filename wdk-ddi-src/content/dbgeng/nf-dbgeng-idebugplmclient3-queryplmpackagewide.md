---
UID: NF:dbgeng.IDebugPlmClient3.QueryPlmPackageWide
title: IDebugPlmClient3::QueryPlmPackageWide (dbgeng.h)
description: Query a Process Lifecycle Management (PLM) package.
old-location: debugger\idebugplmclient3_queryplmpackagewide.htm
tech.root: debugger
ms.assetid: 29BAAEF9-5B69-4723-BC23-A8B668E2A867
ms.date: 05/03/2018
ms.keywords: IDebugPlmClient3 interface [Windows Debugging],QueryPlmPackageWide method, IDebugPlmClient3.QueryPlmPackageWide, IDebugPlmClient3::QueryPlmPackageWide, QueryPlmPackageWide, QueryPlmPackageWide method [Windows Debugging], QueryPlmPackageWide method [Windows Debugging],IDebugPlmClient3 interface, dbgeng/IDebugPlmClient3::QueryPlmPackageWide, debugger.idebugplmclient3_queryplmpackagewide
f1_keywords:
 - "dbgeng/IDebugPlmClient3.QueryPlmPackageWide"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugPlmClient3.QueryPlmPackageWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugPlmClient3::QueryPlmPackageWide


## -description


Query a Process Lifecycle Management (PLM) package.


## -parameters




### -param Server [in]

The server of the package.


### -param PackageFullName [in]

A pointer to the package name.


### -param Stream [in]

A pointer to an output stream for results.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugplmclient3">IDebugPlmClient3</a>
 

 

