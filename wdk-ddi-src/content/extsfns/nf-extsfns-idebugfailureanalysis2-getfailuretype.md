---
UID: NF:extsfns.IDebugFailureAnalysis2.GetFailureType
title: IDebugFailureAnalysis2::GetFailureType (extsfns.h)
description: The GetFailureType method gets the failure type of a DebugFailureAnalysis object. The failure type indicates whether the code being analyzed was running in kernel mode or user mode.
old-location: debugger\idebugfailureanalysis2_getfailuretype.htm
tech.root: debugger
ms.assetid: 3BE85B65-DAE0-41E7-AB24-B5E8E7073E1A
ms.date: 05/03/2018
ms.keywords: GetFailureType, GetFailureType method [Windows Debugging], GetFailureType method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],GetFailureType method, IDebugFailureAnalysis2.GetFailureType, IDebugFailureAnalysis2::GetFailureType, debugger.idebugfailureanalysis2_getfailuretype, extsfns/IDebugFailureAnalysis2::GetFailureType
ms.topic: method
f1_keywords:
 - "extsfns/IDebugFailureAnalysis2.GetFailureType"
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
- IDebugFailureAnalysis2.GetFailureType
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::GetFailureType


## -description


The <b>GetFailureType</b> method gets the failure type of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object. The failure type indicates whether the code being analyzed was running in kernel mode or user mode.


## -returns



This method returns a value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/ne-extsfns-_debug_failure_type">DEBUG_FAILURE_TYPE</a> enumeration.




## -see-also




<b>GetFailureClass</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
 

 

