---
UID: NF:extsfns.IDebugFailureAnalysis2.SetUlong
title: IDebugFailureAnalysis2::SetUlong (extsfns.h)
description: The SetUlong method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified ULONG value.
old-location: debugger\idebugfailureanalysis2_setulong.htm
tech.root: debugger
ms.assetid: 90C0AAE1-EE79-4347-B6F1-276DBF84F7BC
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::SetUlong"]
ms.keywords: IDebugFailureAnalysis2 interface [Windows Debugging],SetUlong method, IDebugFailureAnalysis2.SetUlong, IDebugFailureAnalysis2::SetUlong, SetUlong, SetUlong method [Windows Debugging], SetUlong method [Windows Debugging],IDebugFailureAnalysis2 interface, debugger.idebugfailureanalysis2_setextensionulong, debugger.idebugfailureanalysis2_setulong, extsfns/IDebugFailureAnalysis2::SetUlong
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
 - IDebugFailureAnalysis2::SetUlong
 - extsfns/IDebugFailureAnalysis2::SetUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis2.SetUlong
---

# IDebugFailureAnalysis2::SetUlong


## -description

The <b>SetUlong</b> method searches a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object for the first <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified <b>ULONG</b> value. If this method does not find an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has the specified tag, it creates a new FA entry with that tag and sets the data block of the new FA entry to the specified <b>ULONG</b> value.

## -parameters

### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

### -param Value 

[in]
The <b>ULONG</b> value to be written to the data block of the new or existing <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>.

## -returns

If this method succeeds, it returns a pointer to the new or existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.

## -remarks

If this method finds an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, it checks to see whether the data type associated with that tag is <b>DEBUG_FA_ENTRY_ULONG</b>. If the data type associated with the tag is not <b>DEBUG_FA_ENTRY_ULONG</b>, this method returns NULL and does not overwrite the entry's data block.

If this method does not find an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, it creates a new FA entry with that tag, and it associates the tag with the data type  <b>DEBUG_FA_ENTRY_ULONG</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-addulong">AddUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getulong">GetUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>

