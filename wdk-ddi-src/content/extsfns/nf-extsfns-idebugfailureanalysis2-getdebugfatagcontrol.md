---
UID: NF:extsfns.IDebugFailureAnalysis2.GetDebugFATagControl
title: IDebugFailureAnalysis2::GetDebugFATagControl
author: windows-driver-content
description: The GetDebugFATagControl method gets a pointer to an IDebugFAEntryTags interface, which provides access to the tags in a DebugFailureAnalysisTags object.
old-location: debugger\idebugfailureanalysis2_getdebugfatagcontrol.htm
tech.root: debugger
ms.assetid: AC69BCF1-B5C2-4A2F-AEF0-1BC4EBD0BE66
ms.date: 5/3/2018
ms.keywords: GetDebugFATagControl, GetDebugFATagControl method [Windows Debugging], GetDebugFATagControl method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],GetDebugFATagControl method, IDebugFailureAnalysis2.GetDebugFATagControl, IDebugFailureAnalysis2::GetDebugFATagControl, debugger.idebugfailureanalysis2_getdebugfatagcontrol, extsfns/IDebugFailureAnalysis2::GetDebugFATagControl
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
-	IDebugFailureAnalysis2.GetDebugFATagControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::GetDebugFATagControl


## -description


The <b>GetDebugFATagControl</b> method gets a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a> interface, which provides access to the tags in a DebugFailureAnalysisTags object. For information about the relationship between a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object and a <a href="https://msdn.microsoft.com/B52DFB0E-0035-40C2-B2F5-5E16B16931C2">DebugFailureAnalysisTags</a> object, see <a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Failure Analysis Entries, Tags, and Data Types</a>.


## -parameters




### -param FATagControl [out]

A pointer to a variable that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a> interface.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

