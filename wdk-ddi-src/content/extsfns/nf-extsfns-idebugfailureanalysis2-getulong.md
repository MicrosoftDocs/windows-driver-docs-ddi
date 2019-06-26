---
UID: NF:extsfns.IDebugFailureAnalysis2.GetUlong
title: IDebugFailureAnalysis2::GetUlong (extsfns.h)
description: The GetString method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the ANSI string value from the entry's data block.
old-location: debugger\idebugfailureanalysis2_getstring.htm
tech.root: debugger
ms.assetid: 76F5F3E0-74BF-4DFF-9AA3-A67C03AF56F9
ms.date: 05/03/2018
ms.keywords: GetUlong, GetUlong method [Windows Debugging], GetUlong method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],GetUlong method, IDebugFailureAnalysis2.GetUlong, IDebugFailureAnalysis2::GetUlong, debugger.idebugfailureanalysis2_getstring, extsfns/IDebugFailureAnalysis2::GetUlong
ms.topic: method
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
- IDebugFailureAnalysis2.GetUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::GetUlong


## -description


The <b>GetString</b> method searches a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object for the first <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the ANSI string value from the entry's data block.


## -parameters




### -param Tag [in]

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param Value






#### - MaxSize [in]

The size, in bytes, of the buffer pointed to by <i>Str</i>.


#### - Str [out]

A pointer to a buffer that receives the string value from the entry's data block.


## -returns



If this method finds an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, and if it succeeds in getting the data block, it returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.




## -remarks



This method copies a null-terminated string from the entry's data block to the buffer pointed to by <i>Str</i>. This method copies at most <i>MaxSize</i> characters including the NULL terminator.

Each tag that has already been used in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object is associated with one of the data types in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/ne-extsfns-_fa_entry_type">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a> method of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface. To get a pointer to an IDebugFAEntryTags interface, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-getdebugfatagcontrol">GetDebugFATagControl</a> method of the <b>IDebugFailureAnalysis2</b> interface.

The appropriate use of this method is get the data block from an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a data type of <b>DEBUG_FA_ENTRY_ANSI_STRING</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/print/iprinterbidischemaresponses-addstring">AddString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-setstring">SetString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
 

 

