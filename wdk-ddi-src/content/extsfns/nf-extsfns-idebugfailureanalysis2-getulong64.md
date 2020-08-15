---
UID: NF:extsfns.IDebugFailureAnalysis2.GetUlong64
title: IDebugFailureAnalysis2::GetUlong64 (extsfns.h)
description: The GetUlong64 method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the ULONG64 value from the entry's data block.
old-location: debugger\idebugfailureanalysis2_getulong64.htm
tech.root: debugger
ms.assetid: C00C983A-92BA-4E4A-A5AB-918121D14B64
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::GetUlong64"]
ms.keywords: GetUlong64, GetUlong64 method [Windows Debugging], GetUlong64 method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],GetUlong64 method, IDebugFailureAnalysis2.GetUlong64, IDebugFailureAnalysis2::GetUlong64, debugger.idebugfailureanalysis2_getulong64, extsfns/IDebugFailureAnalysis2::GetUlong64
f1_keywords:
 - "extsfns/IDebugFailureAnalysis2.GetUlong"
 - "IDebugFailureAnalysis2.GetUlong"
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
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::GetUlong64


## -description


The <b>GetUlong64</b> method searches a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object for the first <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the <b>ULONG64</b> value from the entry's data block.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param Value 
[out]
A pointer to a <b>ULONG64</b> that receives the value from the entry's data block.


## -returns



If this method finds an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, and if it succeeds in getting the data block, it returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.




## -remarks



If this method finds an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, it checks to see whether the <b>DataSize</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure is equal to the size of a <b>ULONG64</b>. If <b>DataSize</b> is not equal to the size of a <b>ULONG64</b>, this method returns <b>NULL</b> and does not get the data block.

Each tag that has already been used in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object is associated with one of the data types in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/ne-extsfns-_fa_entry_type">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a> method of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface. To get a pointer to an IDebugFAEntryTags interface, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getdebugfatagcontrol">GetDebugFATagControl</a> method of the <b>IDebugFailureAnalysis2</b> interface.

The appropriate use of this method is get the data block from an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a data type of <b>DEBUG_FA_ENTRY_ULONG64</b> or <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b> or <b>DEBUG_FA_ENTRY_POINTER</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-addulong64">AddUlong64</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-setulong64">SetUlong64</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
 

 

