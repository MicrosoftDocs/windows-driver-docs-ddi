---
UID: NF:extsfns.IDebugFailureAnalysis.NextEntry
title: IDebugFailureAnalysis::NextEntry (extsfns.h)
description: The NextEntry method gets the next FA entry, after a given FA entry, in a DebugFailureAnalysis object.
old-location: debugger\idebugfailureanalysis2_nextentry.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis::NextEntry"]
ms.keywords: IDebugFailureAnalysis interface [Windows Debugging],NextEntry method, IDebugFailureAnalysis.NextEntry, IDebugFailureAnalysis::NextEntry, NextEntry, NextEntry method [Windows Debugging], NextEntry method [Windows Debugging],IDebugFailureAnalysis interface, debugger.idebugfailureanalysis_nextentry, extsfns/IDebugFailureAnalysis::NextEntry
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
 - IDebugFailureAnalysis::NextEntry
 - extsfns/IDebugFailureAnalysis::NextEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis::NextEntry
---

# IDebugFailureAnalysis::NextEntry


## -description

The <b>NextEntry</b> method gets the next <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>, after a given FA entry, in a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis">DebugFailureAnalysis</a> object.

## -parameters

### -param Entry

A pointer to an <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. This method returns the next entry after this entry. If this parameter is <b>NULL</b>, this method returns the first <b>FA_ENTRY</b> in the <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis">DebugFailureAnalysis</a> object.

## -returns

This method returns a pointer to the next (or first) <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. If there are no more <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entries</a> in the <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis">DebugFailureAnalysis</a> object, this method returns <i>NULL</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis-get">Get</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis-getnext">GetNext</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis">IDebugFailureAnalysis</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>

