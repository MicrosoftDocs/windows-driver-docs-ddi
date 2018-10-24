---
UID: NF:extsfns.IDebugFailureAnalysis2.Get
title: IDebugFailureAnalysis2::Get
author: windows-driver-content
description: The Get method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag.
old-location: debugger\idebugfailureanalysis2_get.htm
tech.root: debugger
ms.assetid: 5F43909E-56D0-43F8-A24E-04981614C683
ms.date: 05/03/2018
ms.keywords: Get, Get method [Windows Debugging], Get method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],Get method, IDebugFailureAnalysis2.Get, IDebugFailureAnalysis2::Get, debugger.idebugfailureanalysis2_get, extsfns/IDebugFailureAnalysis2::Get
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
-	IDebugFailureAnalysis2.Get
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::Get


## -description


   The <b>Get</b> method searches a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag.


## -parameters




### -param Tag [in]

A value in  the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


## -returns



If the <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object has any <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entries</a> that have the specified tag, this method returns a pointer to the first <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure that has the specified tag. If the <b>DebugFailureAnalysis</b> object does not have any FA entries that have the specified tag, this method returns <b>NULL</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983418">GetNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983422">NextEntry</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

