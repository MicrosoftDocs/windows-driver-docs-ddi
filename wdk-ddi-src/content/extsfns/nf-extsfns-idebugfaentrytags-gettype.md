---
UID: NF:extsfns.IDebugFAEntryTags.GetType
title: IDebugFAEntryTags::GetType (extsfns.h)
description: The GetType method gets the data type that is associated with a tag in a DebugFailureAnalysisTags object.
old-location: debugger\idebugfaentrytags_gettype.htm
tech.root: debugger
ms.assetid: CE43711F-E17B-4234-A885-4FE04EA53903
ms.date: 05/03/2018
ms.keywords: GetType, GetType method [Windows Debugging], GetType method [Windows Debugging],IDebugFAEntryTags interface, IDebugFAEntryTags interface [Windows Debugging],GetType method, IDebugFAEntryTags.GetType, IDebugFAEntryTags::GetType, debugger.idebugfaentrytags_gettype, extsfns/IDebugFAEntryTags::GetType
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
- IDebugFAEntryTags.GetType
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFAEntryTags::GetType


## -description


The <b>GetType</b> method gets the data type that is associated with a tag in a <a href="https://msdn.microsoft.com/B52DFB0E-0035-40C2-B2F5-5E16B16931C2">DebugFailureAnalysisTags</a> object.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


## -returns



A value in the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991809">FA_ENTRY_TYPE</a> enumeration.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj991816">SetType</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

