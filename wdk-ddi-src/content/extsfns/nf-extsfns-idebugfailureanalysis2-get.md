---
UID: NF:extsfns.IDebugFailureAnalysis2.Get
title: IDebugFailureAnalysis2::Get method
author: windows-driver-content
description: The Get method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag.
old-location: debugger\idebugfailureanalysis2_get.htm
old-project: debugger
ms.assetid: 5F43909E-56D0-43F8-A24E-04981614C683
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugFailureAnalysis2::Get, debugger.idebugfailureanalysis2_get, Get, extsfns/IDebugFailureAnalysis2::Get, IDebugFailureAnalysis2 interface [Windows Debugging], Get method, Get method [Windows Debugging], IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2, Get method [Windows Debugging]
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
-	IDebugFailureAnalysis2.Get
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::Get method


## -description


   The <b>Get</b> method searches a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag.


## -syntax


````
PFA_ENTRY Get(
  [in] FA_TAG Tag
);
````


## -parameters




### -param Tag [in]

A value in  the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


## -returns


If the <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object has any <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entries</a> that have the specified tag, this method returns a pointer to the first <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure that has the specified tag. If the <b>DebugFailureAnalysis</b> object does not have any FA entries that have the specified tag, this method returns <b>NULL</b>. 



## -see-also

<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983422">NextEntry</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983418">GetNext</a>

<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>

<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::Get method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

