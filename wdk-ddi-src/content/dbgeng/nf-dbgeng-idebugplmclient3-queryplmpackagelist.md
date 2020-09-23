---
UID: NF:dbgeng.IDebugPlmClient3.QueryPlmPackageList
title: IDebugPlmClient3::QueryPlmPackageList (dbgeng.h)
description: Query a Process Lifecycle Management (PLM) package list.
old-location: debugger\idebugplmclient3_queryplmpackagelist.htm
tech.root: debugger
ms.assetid: BAAAF09B-F39D-44E0-9409-1C98B0C6A56B
ms.date: 05/03/2018
keywords: ["IDebugPlmClient3::QueryPlmPackageList"]
ms.keywords: IDebugPlmClient3 interface [Windows Debugging],QueryPlmPackageList method, IDebugPlmClient3.QueryPlmPackageList, IDebugPlmClient3::QueryPlmPackageList, QueryPlmPackageList, QueryPlmPackageList method [Windows Debugging], QueryPlmPackageList method [Windows Debugging],IDebugPlmClient3 interface, dbgeng/IDebugPlmClient3::QueryPlmPackageList, debugger.idebugplmclient3_queryplmpackagelist
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
 - IDebugPlmClient3::QueryPlmPackageList
 - dbgeng/IDebugPlmClient3::QueryPlmPackageList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugPlmClient3.QueryPlmPackageList
---

# IDebugPlmClient3::QueryPlmPackageList


## -description

Query a Process Lifecycle Management (PLM) package list.

## -parameters

### -param Server 

[in]
The server of the package.

### -param Stream 

[in]
A pointer to an output stream for results.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugplmclient3">IDebugPlmClient3</a>