---
UID: NF:extsfns.IDebugFailureAnalysis.Get
title: IDebugFailureAnalysis::Get (extsfns.h)
description: The Get method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag.
old-location: debugger\idebugfailureanalysis2_get.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis::Get"]
ms.keywords: Get, Get method [Windows Debugging], Get method [Windows Debugging],IDebugFailureAnalysis interface, IDebugFailureAnalysis interface [Windows Debugging],Get method, IDebugFailureAnalysis.Get, IDebugFailureAnalysis::Get, debugger.idebugfailureAnalysis_get, extsfns/IDebugFailureAnalysis::Get
req.header: extsfns.h
req.include-header: 
req.target-type: Desktop
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
 - IDebugFailureAnalysis::Get
 - extsfns/IDebugFailureAnalysis::Get
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis::Get
---

# IDebugFailureAnalysis::Get


## -description

   The <b>Get</b> method searches a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis">DebugFailureAnalysis</a> object for the first <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a specified tag.

## -parameters

### -param Tag [in]


A value in  the <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

## -returns

If the <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureAnalysis">DebugFailureAnalysis</a> object has any <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entries</a> that have the specified tag, this method returns a pointer to the first <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure that has the specified tag. If the <b>DebugFailureAnalysis</b> object does not have any FA entries that have the specified tag, this method returns <b>NULL</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis-getnext">GetNext</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis">IDebugFailureAnalysis</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis-nextentry">NextEntry</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>

