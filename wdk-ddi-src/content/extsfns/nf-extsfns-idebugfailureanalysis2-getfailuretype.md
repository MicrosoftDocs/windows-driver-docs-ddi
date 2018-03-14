---
UID: NF:extsfns.IDebugFailureAnalysis2.GetFailureType
title: IDebugFailureAnalysis2::GetFailureType method
author: windows-driver-content
description: The GetFailureType method gets the failure type of a DebugFailureAnalysis object. The failure type indicates whether the code being analyzed was running in kernel mode or user mode.
old-location: debugger\idebugfailureanalysis2_getfailuretype.htm
old-project: debugger
ms.assetid: 3BE85B65-DAE0-41E7-AB24-B5E8E7073E1A
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetFailureType method [Windows Debugging], GetFailureType method [Windows Debugging], IDebugFailureAnalysis2 interface, GetFailureType,IDebugFailureAnalysis2.GetFailureType, IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], GetFailureType method, IDebugFailureAnalysis2::GetFailureType, debugger.idebugfailureanalysis2_getfailuretype, extsfns/IDebugFailureAnalysis2::GetFailureType
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
-	IDebugFailureAnalysis2.GetFailureType
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::GetFailureType method


## -description


The <b>GetFailureType</b> method gets the failure type of a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object. The failure type indicates whether the code being analyzed was running in kernel mode or user mode.


## -syntax


````
DEBUG_FAILURE_TYPE GetFailureType();
````


## -parameters






## -returns



This method returns a value in the <a href="..\extsfns\ne-extsfns-_debug_failure_type.md">DEBUG_FAILURE_TYPE</a> enumeration.




## -see-also

<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<b>GetFailureClass</b>



<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>



<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>



 

 


