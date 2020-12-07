---
UID: NF:extsfns.IDebugFAEntryTags.SetType
title: IDebugFAEntryTags::SetType (extsfns.h)
description: The SetType method sets the data type that is associated with a tag in a DebugFailureAnalysisTags object.
old-location: debugger\idebugfaentrytags_settype.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugFAEntryTags::SetType"]
ms.keywords: IDebugFAEntryTags interface [Windows Debugging],SetType method, IDebugFAEntryTags.SetType, IDebugFAEntryTags::SetType, SetType, SetType method [Windows Debugging], SetType method [Windows Debugging],IDebugFAEntryTags interface, debugger.idebugfaentrytags_settype, extsfns/IDebugFAEntryTags::SetType
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
 - IDebugFAEntryTags::SetType
 - extsfns/IDebugFAEntryTags::SetType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFAEntryTags.SetType
---

# IDebugFAEntryTags::SetType


## -description

The <b>SetType</b> method sets the data type that is associated with a tag in a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">DebugFailureAnalysisTags</a> object.

## -parameters

### -param Tag 

[in]
A value in the <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

### -param EntryType 

[in]
A value in the <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_ENTRY_TYPE</a> enumeration.

## -returns

If this method successfully sets the data type of <i>Tag</i> to <i>EntryType</i>, it returns <b>S_OK</b>. Otherwise, it returns <b>E_INVALIDARG</b>.

## -remarks

This method checks to see whether the data type for <i>Tag</i> has already been set. If the data type has not already been set, this method sets the data type to <i>EntryType</i>.

If the data type for <i>Tag</i> has already been set, this method checks to see whether <i>EntryType</i> is compatible with the data type that has already been set. If the data types are compatible, this method sets (overwrites) the data type for <i>Tag</i> to <i>EntryType</i>. If the data types are not compatible, this method returns <b>E_INVALIDARG</b> and does not set the data type.

The data types <b>DEBUG_FA_ENTRY_ULONG64</b>, <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b>, and <b>DEBUG_FA_ENTRY_POINTER</b> are compatible.

The data types <b>DEBUG_FA_ENTRY_ANSI_STRING</b> and <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b> are compatible.

## -see-also

<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
