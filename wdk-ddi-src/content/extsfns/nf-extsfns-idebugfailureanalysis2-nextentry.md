---
UID: NF:extsfns.IDebugFailureAnalysis2.NextEntry
title: IDebugFailureAnalysis2::NextEntry method
author: windows-driver-content
description: The NextEntry method gets the next FA entry, after a given FA entry, in a DebugFailureAnalysis object.
old-location: debugger\idebugfailureanalysis2_nextentry.htm
old-project: debugger
ms.assetid: B5640B86-D931-4A26-85F2-BBE18620668C
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugFailureAnalysis2, IDebugFailureAnalysis2::NextEntry, NextEntry method [Windows Debugging], NextEntry method [Windows Debugging], IDebugFailureAnalysis2 interface, NextEntry, IDebugFailureAnalysis2 interface [Windows Debugging], NextEntry method, debugger.idebugfailureanalysis2_nextentry, extsfns/IDebugFailureAnalysis2::NextEntry
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
-	IDebugFailureAnalysis2.NextEntry
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::NextEntry method


## -description


The <b>NextEntry</b> method gets the next <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after a given FA entry, in a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object.


## -syntax


````
PFA_ENTRY NextEntry(
   PFA_ENTRY  Entry
);
````


## -parameters




### -param Entry

A pointer to an <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure. This method returns the next entry after this entry. If this parameter is <b>NULL</b>, this method returns the first <b>FA_ENTRY</b> in the <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object.


## -returns


This method returns a pointer to the next (or first) <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure. If there are no more <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entries</a> in the <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object, this method returns <i>NULL</i>.



## -see-also

<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>

<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983418">GetNext</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983411">Get</a>

<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::NextEntry method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

