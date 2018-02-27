---
UID: NF:extsfns.IDebugFailureAnalysis2.GetFailureCode
title: IDebugFailureAnalysis2::GetFailureCode method
author: windows-driver-content
description: The GetFailureCode method gets the bug check code or exception code of a DebugFailureAnalysis object.
old-location: debugger\idebugfailureanalysis2_getfailurecode.htm
old-project: debugger
ms.assetid: E407482E-26DD-40C6-9405-DF5CA8996B91
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetFailureCode method [Windows Debugging], GetFailureCode method [Windows Debugging], IDebugFailureAnalysis2 interface, GetFailureCode,IDebugFailureAnalysis2.GetFailureCode, IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], GetFailureCode method, IDebugFailureAnalysis2::GetFailureCode, debugger.idebugfailureanalysis2_getfailurecode, extsfns/IDebugFailureAnalysis2::GetFailureCode
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	extsfns.h
api_name:
-	IDebugFailureAnalysis2.GetFailureCode
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::GetFailureCode method


## -description


The <b>GetFailureCode</b> method gets the bug check code or exception code of a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object.


## -syntax


````
ULONG GetFailureCode();
````


## -parameters






## -returns



This method returns a <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">bug check code</a> or an <a href="http://go.microsoft.com/fwlink/p?LinkID=282670">exception code</a>.




## -remarks



When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562112">!analyze</a> debugger command runs in response to a code failure, the analysis engine creates a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object to store data that describes and categorizes the failure. If the failure being analyzed is a bug check, this method returns a bug check code. If the failure being analyzed is an exception, this method returns an exception code.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983415">GetFailureClass</a>



<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983417">GetFailureType</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::GetFailureCode method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

