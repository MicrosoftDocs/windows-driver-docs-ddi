---
UID: NF:extsfns.IDebugFAEntryTags.IsValidTagToSet
title: IDebugFAEntryTags::IsValidTagToSet method
author: windows-driver-content
description: The IsValidTagToSet method determines whether it is OK to set the data of a specified tag.
old-location: debugger\idebugfaentrytags_isvalidtagtoset.htm
old-project: debugger
ms.assetid: 83B5C54F-182B-4D2F-8ED2-7A0B529F1D2E
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugFAEntryTags, IDebugFAEntryTags interface [Windows Debugging], IsValidTagToSet method, IDebugFAEntryTags::IsValidTagToSet, IsValidTagToSet method [Windows Debugging], IsValidTagToSet method [Windows Debugging], IDebugFAEntryTags interface, IsValidTagToSet,IDebugFAEntryTags.IsValidTagToSet, debugger.idebugfaentrytags_isvalidtagtoset, extsfns/IDebugFAEntryTags::IsValidTagToSet
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
-	IDebugFAEntryTags.IsValidTagToSet
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFAEntryTags::IsValidTagToSet method


## -description


The <b>IsValidTagToSet</b> method determines whether it is OK to set the data of a specified tag.


## -syntax


````
BOOL IsValidTagToSet(
   FA_TAG Tag
);
````


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


## -returns



This method returns TRUE if it is OK to set the data of the specified tag. Otherwise it returns FALSE.




## -see-also

<a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>



<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>



 

 


