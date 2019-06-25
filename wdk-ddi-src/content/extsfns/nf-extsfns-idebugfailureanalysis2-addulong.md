---
UID: NF:extsfns.IDebugFailureAnalysis2.AddUlong
title: IDebugFailureAnalysis2::AddUlong (extsfns.h)
description: The AddUlong method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified ULONG value.
old-location: debugger\idebugfailureanalysis2_addulong.htm
tech.root: debugger
ms.assetid: 22F56E3F-9ED4-464D-B97C-1B322E1F8D66
ms.date: 05/03/2018
ms.keywords: AddUlong, AddUlong method [Windows Debugging], AddUlong method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],AddUlong method, IDebugFailureAnalysis2.AddUlong, IDebugFailureAnalysis2::AddUlong, debugger.idebugfailureanalysis2_addulong, extsfns/IDebugFailureAnalysis2::AddUlong
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
- IDebugFailureAnalysis2.AddUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::AddUlong


## -description


The <b>AddUlong</b> method adds a new <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>  to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object and sets the data block of the FA entry to a specified <b>ULONG</b> value.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration. The data type associated with this tag must be <b>DEBUG_FA_ENTRY_ULONG</b>.


### -param Value [in]

The <b>ULONG</b> value to be written to the data block of the new <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>.


## -returns



If this method succeeds, it returns a returns a pointer to the new <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. If this method fails, it returns <b>NULL</b>.




## -remarks



Each tag is associated with one of the data types in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/ne-extsfns-_fa_entry_type">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a> method of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface.

To get a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a> interface, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-getdebugfatagcontrol">GetDebugFATagControl</a> method of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a> interface. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-getulong">GetUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-setulong">SetUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
 

 

