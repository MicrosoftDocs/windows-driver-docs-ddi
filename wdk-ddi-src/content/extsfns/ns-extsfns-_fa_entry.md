---
UID: NS:extsfns._FA_ENTRY
title: _FA_ENTRY (extsfns.h)
description: A DebugFailureAnalysis object has a collection of failure analysis entries (FA entries). Each FA entry is represented by an FA_ENTRY structure. For more information, see Failure Analysis Entries, Tags, and Data Types.
old-location: debugger\fa_entry.htm
tech.root: debugger
ms.assetid: 912DCC1E-2C81-4702-8E12-6331DFB298F0
ms.date: 05/03/2018
keywords: ["FA_ENTRY structure"]
ms.keywords: "*PFA_ENTRY, FA_ENTRY, FA_ENTRY structure [Windows Debugging], _FA_ENTRY, debugger.fa_entry, extsfns/FA_ENTRY"
req.header: extsfns.h
req.include-header: 
req.target-type: Windows
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
req.typenames: FA_ENTRY, *PFA_ENTRY
f1_keywords:
 - _FA_ENTRY
 - extsfns/_FA_ENTRY
 - PFA_ENTRY
 - extsfns/PFA_ENTRY
 - FA_ENTRY
 - extsfns/FA_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - extsfns.h
api_name:
 - FA_ENTRY
---

# _FA_ENTRY structure


## -description

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object has a collection of <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">failure analysis entries</a> (FA entries).  Each FA entry is represented by an <b>FA_ENTRY</b> structure. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Failure Analysis Entries, Tags, and Data Types</a>.

## -struct-fields

### -field Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

### -field FullSize

The size of the of <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>, which includes the size of the <b>FA_ENTRY</b> structure and the size of the FA entry's data block.

### -field DataSize

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry's</a> data block.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">Failure Analysis Entries</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>

