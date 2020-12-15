---
UID: NF:extsfns.IDebugFailureAnalysis2.AddUlong64
title: IDebugFailureAnalysis2::AddUlong64 (extsfns.h)
description: The AddUlong64 method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified 64-bit value.
old-location: debugger\idebugfailureanalysis2_addulong64.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::AddUlong64"]
ms.keywords: AddUlong64, AddUlong64 method [Windows Debugging], AddUlong64 method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],AddUlong64 method, IDebugFailureAnalysis2.AddUlong64, IDebugFailureAnalysis2::AddUlong64, debugger.idebugfailureanalysis2_addulong64, extsfns/IDebugFailureAnalysis2::AddUlong64
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
 - IDebugFailureAnalysis2::AddUlong64
 - extsfns/IDebugFailureAnalysis2::AddUlong64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis2.AddUlong64
---

# IDebugFailureAnalysis2::AddUlong64


## -description

The <b>AddUlong64</b> method adds a new <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>  to a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object and sets the data block of the FA entry to a specified 64-bit value.

## -parameters

### -param Tag

A value in the <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration. The data type associated with this tag must be <b>DEBUG_FA_ENTRY_ULONG64</b> or <b>DEBUG_FA_ENTRY_POINTER</b> or <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b>.

### -param Value 

[in]
The <b>ULONG64</b> value to be written to the data block of the new <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>.

## -returns

If this method succeeds, it returns a returns a pointer to the new <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. If this method fails, it returns <b>NULL</b>.

## -remarks

Each tag is associated with one of the data types in the <a href="/windows-hardware/drivers/ddi/extsfns/ne-extsfns-_fa_entry_type">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a> method of the <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface.

To get a pointer to an <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface, call the <a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getdebugfatagcontrol">GetDebugFATagControl</a> method of the <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a> interface.

## -see-also

<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getulong64">GetUlong64</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-setulong64">SetUlong64</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
