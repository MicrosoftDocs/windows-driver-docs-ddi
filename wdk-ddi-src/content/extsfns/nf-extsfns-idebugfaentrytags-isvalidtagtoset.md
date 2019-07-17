---
UID: NF:extsfns.IDebugFAEntryTags.IsValidTagToSet
title: IDebugFAEntryTags::IsValidTagToSet (extsfns.h)
description: The IsValidTagToSet method determines whether it is OK to set the data of a specified tag.
old-location: debugger\idebugfaentrytags_isvalidtagtoset.htm
tech.root: debugger
ms.assetid: 83B5C54F-182B-4D2F-8ED2-7A0B529F1D2E
ms.date: 05/03/2018
ms.keywords: IDebugFAEntryTags interface [Windows Debugging],IsValidTagToSet method, IDebugFAEntryTags.IsValidTagToSet, IDebugFAEntryTags::IsValidTagToSet, IsValidTagToSet, IsValidTagToSet method [Windows Debugging], IsValidTagToSet method [Windows Debugging],IDebugFAEntryTags interface, debugger.idebugfaentrytags_isvalidtagtoset, extsfns/IDebugFAEntryTags::IsValidTagToSet
ms.topic: method
f1_keywords:
 - "extsfns/IDebugFAEntryTags.IsValidTagToSet"
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
- IDebugFAEntryTags.IsValidTagToSet
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFAEntryTags::IsValidTagToSet


## -description


The <b>IsValidTagToSet</b> method determines whether it is OK to set the data of a specified tag.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


## -returns



This method returns TRUE if it is OK to set the data of the specified tag. Otherwise it returns FALSE.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
 

 

