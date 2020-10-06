---
UID: NF:extsfns.IDebugFailureAnalysis2.GetDebugFATagControl
title: IDebugFailureAnalysis2::GetDebugFATagControl (extsfns.h)
description: The GetDebugFATagControl method gets a pointer to an IDebugFAEntryTags interface, which provides access to the tags in a DebugFailureAnalysisTags object.
old-location: debugger\idebugfailureanalysis2_getdebugfatagcontrol.htm
tech.root: debugger
ms.assetid: AC69BCF1-B5C2-4A2F-AEF0-1BC4EBD0BE66
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::GetDebugFATagControl"]
ms.keywords: GetDebugFATagControl, GetDebugFATagControl method [Windows Debugging], GetDebugFATagControl method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],GetDebugFATagControl method, IDebugFailureAnalysis2.GetDebugFATagControl, IDebugFailureAnalysis2::GetDebugFATagControl, debugger.idebugfailureanalysis2_getdebugfatagcontrol, extsfns/IDebugFailureAnalysis2::GetDebugFATagControl
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
 - IDebugFailureAnalysis2::GetDebugFATagControl
 - extsfns/IDebugFailureAnalysis2::GetDebugFATagControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis2.GetDebugFATagControl
---

# IDebugFailureAnalysis2::GetDebugFATagControl


## -description

The <b>GetDebugFATagControl</b> method gets a pointer to an <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface, which provides access to the tags in a DebugFailureAnalysisTags object. For information about the relationship between a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object and a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">DebugFailureAnalysisTags</a> object, see <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Failure Analysis Entries, Tags, and Data Types</a>.

## -parameters

### -param FATagControl 

[out]
A pointer to a variable that receives a pointer to the <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface.

## -returns

This method does not return a value.

## -see-also

<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>