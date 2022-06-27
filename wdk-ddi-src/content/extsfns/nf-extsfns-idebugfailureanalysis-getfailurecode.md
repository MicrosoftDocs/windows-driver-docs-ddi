---
UID: NF:extsfns.IDebugFailureAnalysis.GetFailureCode
title: IDebugFailureAnalysis::GetFailureCode (extsfns.h)
description: The GetFailureCode method gets the bug check code or exception code of a DebugFailureAnalysis object.
old-location: debugger\idebugfailureanalysis2_getfailurecode.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::GetFailureCode"]
ms.keywords: GetFailureCode, GetFailureCode method [Windows Debugging], GetFailureCode method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],GetFailureCode method, IDebugFailureAnalysis2.GetFailureCode, IDebugFailureAnalysis2::GetFailureCode, debugger.idebugfailureanalysis2_getfailurecode, extsfns/IDebugFailureAnalysis2::GetFailureCode
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
 - IDebugFailureAnalysis2::GetFailureCode
 - extsfns/IDebugFailureAnalysis2::GetFailureCode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis2::GetFailureCode
---

# IDebugFailureAnalysis2::GetFailureCode


## -description

The <b>GetFailureCode</b> method gets the bug check code or exception code of a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object.

## -returns

This method returns a <a href="/windows-hardware/drivers/debugger/bug-check-code-reference2">bug check code</a> or an <a href="/windows/win32/debug/structured-exception-handling">exception code</a>.

## -remarks

When the <a href="/windows-hardware/drivers/debugger/-analyze">!analyze</a> debugger command runs in response to a code failure, the analysis engine creates a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object to store data that describes and categorizes the failure. If the failure being analyzed is a bug check, this method returns a bug check code. If the failure being analyzed is an exception, this method returns an exception code.

## -see-also

<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getfailureclass">GetFailureClass</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getfailuretype">GetFailureType</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>

