---
UID: NF:extsfns.IDebugFailureAnalysis.GetUlong
title: IDebugFailureAnalysis::GetUlong (extsfns.h)
description: The GetUlong method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag.
old-location: debugger\idebugfailureanalysis2_getstring.htm
tech.root: debugger
ms.date: 06/16/2022
keywords: ["IDebugFailureAnalysis::GetUlong"]
ms.keywords: GetUlong, GetUlong method [Windows Debugging], GetUlong method [Windows Debugging],IDebugFailureAnalysis interface, IDebugFailureAnalysis interface [Windows Debugging],GetUlong method, IDebugFailureAnalysis.GetUlong, IDebugFailureAnalysis::GetUlong, debugger.IDebugFailureAnalysis_getstring, extsfns/IDebugFailureAnalysis2::GetUlong
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
 - IDebugFailureAnalysis::GetUlong
 - extsfns/IDebugFailureAnalysis::GetUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis::GetUlong
---

# IDebugFailureAnalysis::GetUlong


## -description

The <b>GetUlong</b> method searches a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object for the first <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the ANSI string value from the entry's data block.

## -parameters

### -param Tag [in]


A value in the <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

### -param Value

### -param MaxSize [in]

The size, in bytes, of the buffer pointed to by <i>Str</i>.


### -param Str [out]

A pointer to a buffer that receives the string value from the entry's data block.

## -returns

If this method finds an <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, and if it succeeds in getting the data block, it returns a pointer to the <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.

## -remarks

This method copies a null-terminated string from the entry's data block to the buffer pointed to by <i>Str</i>. This method copies at most <i>MaxSize</i> characters including the NULL terminator.

Each tag that has already been used in a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object is associated with one of the data types in the <a href="/windows-hardware/drivers/ddi/extsfns/ne-extsfns-_fa_entry_type">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a> method of the <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface. To get a pointer to an IDebugFAEntryTags interface, call the <a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getdebugfatagcontrol">GetDebugFATagControl</a> method of the <b>IDebugFailureAnalysis2</b> interface.

The appropriate use of this method is get the data block from an <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a data type of <b>DEBUG_FA_ENTRY_ANSI_STRING</b>.

## -see-also

<a href="/windows-hardware/drivers/print/iprinterbidischemaresponses-addstring">AddString</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-setstring">SetString</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>

