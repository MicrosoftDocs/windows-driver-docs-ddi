---
UID: NF:extsfns.IDebugFailureAnalysis2.GetBuffer
title: IDebugFailureAnalysis2::GetBuffer (extsfns.h)
description: The GetBuffer method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the entry's data block.
old-location: debugger\idebugfailureanalysis2_getbuffer.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::GetBuffer"]
ms.keywords: GetBuffer, GetBuffer method [Windows Debugging], GetBuffer method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],GetBuffer method, IDebugFailureAnalysis2.GetBuffer, IDebugFailureAnalysis2::GetBuffer, debugger.idebugfailureanalysis2_getbuffer, extsfns/IDebugFailureAnalysis2::GetBuffer
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
 - IDebugFailureAnalysis2::GetBuffer
 - extsfns/IDebugFailureAnalysis2::GetBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis2.GetBuffer
---

# IDebugFailureAnalysis2::GetBuffer


## -description

The <b>GetBuffer</b> method searches a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object for the first <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the entry's data block.

## -parameters

### -param Tag 

[in]
A value in the <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

### -param Buf 

[out]
A pointer to a buffer that receives the entry's data block.

### -param Size 

[in]
The size, in bytes, of the buffer pointed to by <i>Buf</i>.

## -returns

If this method finds an <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, and if it succeeds in getting the data block, it returns a pointer to the <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.

## -remarks

If this method finds an <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, it checks to see whether the <b>DataSize</b> member of the <a href="/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure is equal to the value specified by the <i>Size</i> parameter. If <b>DataSize</b> is not equal to <i>Size</i>, this method returns <b>NULL</b> and does not get the data block.

## -see-also

<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-addbuffer">AddBuffer</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-setbuffer">SetBuffer</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
