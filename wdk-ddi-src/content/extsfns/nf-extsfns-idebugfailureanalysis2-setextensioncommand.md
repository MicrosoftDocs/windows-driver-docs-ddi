---
UID: NF:extsfns.IDebugFailureAnalysis2.SetExtensionCommand
title: IDebugFailureAnalysis2::SetExtensionCommand (extsfns.h)
description: The SetExtensionCommand method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag.
old-location: debugger\idebugfailureanalysis2_setextensioncommand.htm
tech.root: debugger
ms.assetid: 741B3D1F-FA7B-4260-AD0C-461D76605CBA
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::SetExtensionCommand"]
ms.keywords: IDebugFailureAnalysis2 interface [Windows Debugging],SetExtensionCommand method, IDebugFailureAnalysis2.SetExtensionCommand, IDebugFailureAnalysis2::SetExtensionCommand, SetExtensionCommand, SetExtensionCommand method [Windows Debugging], SetExtensionCommand method [Windows Debugging],IDebugFailureAnalysis2 interface, debugger.idebugfailureanalysis2_setextensioncommand, extsfns/IDebugFailureAnalysis2::SetExtensionCommand
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
 - IDebugFailureAnalysis2::SetExtensionCommand
 - extsfns/IDebugFailureAnalysis2::SetExtensionCommand
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis2.SetExtensionCommand
---

# IDebugFailureAnalysis2::SetExtensionCommand


## -description

The <b>SetExtensionCommand</b> method searches a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object for the first <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified extension command string. If this method does not find an <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has the specified tag, it creates a new FA entry with that tag and sets the data block of the new FA entry to the specified extension command string.

## -parameters

### -param Tag

A value in the <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

### -param Extension

A pointer to a null-terminated string that is the extension command. An example of an extension command is "!analyze -v".

## -returns

If this method succeeds, it returns a pointer to the new or existing <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.

## -remarks

If this method finds an <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, it checks to see whether the data type associated with that tag is <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b> or <b>DEBUG_FA_ENTRY_ANSI_STRING</b>. If the data type associated with the tag does not have one of those two values, this method returns <b>NULL</b> and does not overwrite the entry's data block.

If this method does not find an <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, it creates a new FA entry with that tag, and it associates the tag with the data type  <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-addextensioncommand">AddExtensionCommand</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>