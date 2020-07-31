---
UID: NF:extsfns.IDebugFAEntryTags.SetProperties
title: IDebugFAEntryTags::SetProperties (extsfns.h)
description: The SetProperties method sets the name or description (or both) of a tag in a DebugFailureAnalysisTags object.
old-location: debugger\idebugfaentrytags_setproperties.htm
tech.root: debugger
ms.assetid: EEBD3291-4DFC-4503-9F5A-49591FE09680
ms.date: 05/03/2018
keywords: ["IDebugFAEntryTags::SetProperties"]
ms.keywords: IDebugFAEntryTags interface [Windows Debugging],SetProperties method, IDebugFAEntryTags.SetProperties, IDebugFAEntryTags::SetProperties, SetProperties, SetProperties method [Windows Debugging], SetProperties method [Windows Debugging],IDebugFAEntryTags interface, debugger.idebugfaentrytags_setproperties, extsfns/IDebugFAEntryTags::SetProperties
f1_keywords:
 - "extsfns/IDebugFAEntryTags.SetProperties"
 - "IDebugFAEntryTags.SetProperties"
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
- IDebugFAEntryTags.SetProperties
targetos: Windows
req.typenames: 
---

# IDebugFAEntryTags::SetProperties


## -description


The <b>SetProperties</b> method sets the name or description (or both) of a tag in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">DebugFailureAnalysisTags</a> object. 


## -parameters




### -param Tag [in]

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration. This method sets the name or description (or both) of this tag.


### -param Name [in]

A pointer to a null-terminated string that specifies the name to be set. If the tag already has a name, this method overwrites the old name. If this parameter is <b>NULL</b>, the name of the tag is not changed.


### -param Description [in]

A pointer to a null-terminated string that specifies the description to be set. If the tag already has a description, this method overwrites the old description. If this parameter is <b>NULL</b>, the description of the tag is not changed.


### -param Flags [in]

Reserved. Set this parameter to <b>NULL</b>.


## -returns



If this method succeeds, it returns <b>S_OK</b>. Otherwise it returns an error code. Error codes are defined in winerror.h and strsafe.h.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-getproperties">GetProperties</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
 

 

