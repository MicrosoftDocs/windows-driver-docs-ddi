---
UID: NF:extsfns.IDebugFailureAnalysis2.SetString
title: IDebugFailureAnalysis2::SetString (extsfns.h)
description: The SetString method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified string value.
old-location: debugger\idebugfailureanalysis2_setstring.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::SetString"]
ms.keywords: IDebugFailureAnalysis2 interface [Windows Debugging],SetString method, IDebugFailureAnalysis2.SetString, IDebugFailureAnalysis2::SetString, SetString, SetString method [Windows Debugging], SetString method [Windows Debugging],IDebugFailureAnalysis2 interface, debugger.idebugfailureanalysis2_setstring, extsfns/IDebugFailureAnalysis2::SetString
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
 - IDebugFailureAnalysis2::SetString
 - extsfns/IDebugFailureAnalysis2::SetString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis2::SetString
---

# IDebugFailureAnalysis2::SetString


## -description

The <b>SetString</b> method searches a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object for the first <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified string value.  If this method does not find an <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has the specified tag, it creates a new FA entry with that tag and sets the data block of the new FA entry to the specified string value.

## -parameters

### -param Tag

A value in the <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

### -param Str 

[in]
A pointer to a null-terminated ANSI string to be written to the data block of the new or existing <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>.

## -returns

If this method succeeds, it returns a pointer to the new or existing <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.

## -remarks

If this method finds an <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, it checks to see whether the data type associated with that tag is <b>DEBUG_FA_ENTRY_ANSI_STRING</b> or <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b>. If the data type associated with the tag is not one of those two types, this method returns <b>NULL</b> and does not overwrite the entry's data block.

If this method does not find an <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, it creates a new FA entry with that tag, and it associates the tag with the data type  <b>DEBUG_FA_ENTRY_ANSI_STRING</b>.

## -see-also

<a href="/windows-hardware/drivers/print/iprinterbidischemaresponses-addstring">AddString</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getstring">GetString</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>

