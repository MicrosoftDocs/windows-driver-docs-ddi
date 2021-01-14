---
UID: NF:extsfns.IDebugFailureAnalysis2.AddString
title: IDebugFailureAnalysis2::AddString (extsfns.h)
description: The AddString method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified string.
old-location: debugger\idebugfailureanalysis2_addstring.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::AddString"]
ms.keywords: AddString, AddString method [Windows Debugging], AddString method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],AddString method, IDebugFailureAnalysis2.AddString, IDebugFailureAnalysis2::AddString, debugger.idebugfailureanalysis2_addstring, extsfns/IDebugFailureAnalysis2::AddString
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
 - IDebugFailureAnalysis2::AddString
 - extsfns/IDebugFailureAnalysis2::AddString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis2::AddString
---

# IDebugFailureAnalysis2::AddString


## -description

The <b>AddString</b> method adds a new <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> to a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object and sets the data block of the FA entry to a specified string.

## -parameters

### -param Tag

A value in the <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration. The data type associated with this tag must be <b>DEBUG_FA_ENTRY_ANSI_STRING</b>.

### -param Str 

[in]
A pointer to a null-terminated ANSI string to be written to the data block of the new <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>.

## -returns

If this method succeeds, it returns a returns a pointer to the new <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. If this method fails, it returns <b>NULL</b>.

## -remarks

This method sets the <b>DataSize</b> member of the new <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure to the length, in bytes, of the string including the <b>NULL</b> terminator.

Each tag is associated with one of the data types in the <a href="/windows-hardware/drivers/ddi/extsfns/ne-extsfns-_fa_entry_type">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a> method of the <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface.

To get a pointer to an <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface, call the <a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getdebugfatagcontrol">GetDebugFATagControl</a> method of the <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a> interface.

## -see-also

<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getstring">GetString</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-setstring">SetString</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>

