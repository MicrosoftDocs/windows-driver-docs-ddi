---
UID: NF:extsfns.IDebugFailureAnalysis2.GetDebugFATagControl
title: IDebugFailureAnalysis2::GetDebugFATagControl method
author: windows-driver-content
description: The GetDebugFATagControl method gets a pointer to an IDebugFAEntryTags interface, which provides access to the tags in a DebugFailureAnalysisTags object.
old-location: debugger\idebugfailureanalysis2_getdebugfatagcontrol.htm
old-project: debugger
ms.assetid: AC69BCF1-B5C2-4A2F-AEF0-1BC4EBD0BE66
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: extsfns/IDebugFailureAnalysis2::GetDebugFATagControl, GetDebugFATagControl method [Windows Debugging], IDebugFailureAnalysis2::GetDebugFATagControl, IDebugFailureAnalysis2, GetDebugFATagControl, IDebugFailureAnalysis2 interface [Windows Debugging], GetDebugFATagControl method, debugger.idebugfailureanalysis2_getdebugfatagcontrol, GetDebugFATagControl method [Windows Debugging], IDebugFailureAnalysis2 interface
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
req.lib: extsfns.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	extsfns.h
apiname:
-	IDebugFailureAnalysis2.GetDebugFATagControl
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::GetDebugFATagControl method


## -description


The <b>GetDebugFATagControl</b> method gets a pointer to an <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a> interface, which provides access to the tags in a DebugFailureAnalysisTags object. For information about the relationship between a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object and a <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">DebugFailureAnalysisTags</a> object, see <a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Failure Analysis Entries, Tags, and Data Types</a>.


## -syntax


````
VOID GetDebugFATagControl(
  [out] IDebugFAEntryTags** FATagControl
);
````


## -parameters




### -param FATagControl [out]

A pointer to a variable that receives a pointer to the <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a> interface.


## -returns


This method does not return a value.



## -see-also

<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>

<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>

<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::GetDebugFATagControl method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

