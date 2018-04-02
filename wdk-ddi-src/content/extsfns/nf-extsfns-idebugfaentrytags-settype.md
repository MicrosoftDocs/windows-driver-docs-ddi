---
UID: NF:extsfns.IDebugFAEntryTags.SetType
title: IDebugFAEntryTags::SetType method
author: windows-driver-content
description: The SetType method sets the data type that is associated with a tag in a DebugFailureAnalysisTags object.
old-location: debugger\idebugfaentrytags_settype.htm
old-project: debugger
ms.assetid: F507864B-B20C-4F71-B068-802780243106
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugFAEntryTags, IDebugFAEntryTags interface [Windows Debugging], SetType method, IDebugFAEntryTags::SetType, SetType method [Windows Debugging], SetType method [Windows Debugging], IDebugFAEntryTags interface, SetType,IDebugFAEntryTags.SetType, debugger.idebugfaentrytags_settype, extsfns/IDebugFAEntryTags::SetType
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	extsfns.h
api_name:
-	IDebugFAEntryTags.SetType
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFAEntryTags::SetType method


## -description


The <b>SetType</b> method sets the data type that is associated with a tag in a <a href="https://msdn.microsoft.com/B52DFB0E-0035-40C2-B2F5-5E16B16931C2">DebugFailureAnalysisTags</a> object.


## -parameters




### -param Tag [in]

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param EntryType [in]

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_ENTRY_TYPE</a> enumeration.


## -returns



If this method successfully sets the data type of <i>Tag</i> to <i>EntryType</i>, it returns <b>S_OK</b>. Otherwise, it returns <b>E_INVALIDARG</b>.




## -remarks



This method checks to see whether the data type for <i>Tag</i> has already been set. If the data type has not already been set, this method sets the data type to <i>EntryType</i>.

If the data type for <i>Tag</i> has already been set, this method checks to see whether <i>EntryType</i> is compatible with the data type that has already been set. If the data types are compatible, this method sets (overwrites) the data type for <i>Tag</i> to <i>EntryType</i>. If the data types are not compatible, this method returns <b>E_INVALIDARG</b> and does not set the data type.

The data types <b>DEBUG_FA_ENTRY_ULONG64</b>, <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b>, and <b>DEBUG_FA_ENTRY_POINTER</b> are compatible.

The data types <b>DEBUG_FA_ENTRY_ANSI_STRING</b> and <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b> are compatible.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

