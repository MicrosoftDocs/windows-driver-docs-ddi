---
UID: NF:extsfns.IDebugFailureAnalysis2.NextEntry
title: IDebugFailureAnalysis2::NextEntry (extsfns.h)
description: The NextEntry method gets the next FA entry, after a given FA entry, in a DebugFailureAnalysis object.
old-location: debugger\idebugfailureanalysis2_nextentry.htm
tech.root: debugger
ms.assetid: B5640B86-D931-4A26-85F2-BBE18620668C
ms.date: 05/03/2018
ms.keywords: IDebugFailureAnalysis2 interface [Windows Debugging],NextEntry method, IDebugFailureAnalysis2.NextEntry, IDebugFailureAnalysis2::NextEntry, NextEntry, NextEntry method [Windows Debugging], NextEntry method [Windows Debugging],IDebugFailureAnalysis2 interface, debugger.idebugfailureanalysis2_nextentry, extsfns/IDebugFailureAnalysis2::NextEntry
ms.topic: method
f1_keywords:
 - "extsfns/IDebugFailureAnalysis2.NextEntry"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- extsfns.h
api_name:
- IDebugFailureAnalysis2.NextEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::NextEntry


## -description


The <b>NextEntry</b> method gets the next <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>, after a given FA entry, in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object.


## -parameters




### -param Entry

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. This method returns the next entry after this entry. If this parameter is <b>NULL</b>, this method returns the first <b>FA_ENTRY</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object.


## -returns



This method returns a pointer to the next (or first) <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. If there are no more <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entries</a> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object, this method returns <i>NULL</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-get">Get</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-getnext">GetNext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
 

 

