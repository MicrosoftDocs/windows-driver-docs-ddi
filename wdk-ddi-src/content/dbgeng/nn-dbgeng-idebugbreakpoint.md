---
UID: NN:dbgeng.IDebugBreakpoint
title: IDebugBreakpoint (dbgeng.h)
description: IDebugBreakpoint interface
old-location: debugger\idebugbreakpoint.htm
tech.root: debugger
ms.assetid: ad4bcabb-304e-4427-9b0d-2e22429e8cdd
ms.date: 05/03/2018
ms.keywords: ComOther_93345db9-13c0-4b46-be4a-d3fbb6039cc7.xml, IDebugBreakpoint, IDebugBreakpoint interface [Windows Debugging], IDebugBreakpoint interface [Windows Debugging],described, dbgeng/IDebugBreakpoint, debugger.idebugbreakpoint
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugBreakpoint"
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
- IDebugBreakpoint
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugBreakpoint</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugBreakpoint</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



Although <b>IDebugBreakpoint</b> implements the <b>IUnknown</b> interface, the <b>IUnknown::AddRef</b> and <b>IUnknown::Release</b> methods are not used to control the lifetime of the breakpoint. Instead, an <b>IDebugBreakpoint</b> object is deleted after the method <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removebreakpoint">RemoveBreakpoint</a> is called.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugbreakpoint2">IDebugBreakpoint2</a>
 

 

