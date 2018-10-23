---
UID: NF:extsfns.IDebugFailureAnalysis2.AddBuffer
title: IDebugFailureAnalysis2::AddBuffer
author: windows-driver-content
description: The AddBuffer method adds a new FA entry to a DebugFailureAnalysis object, and writes the bytes from a specified buffer to the data block of the new FA entry.
old-location: debugger\idebugfailureanalysis2_addbuffer.htm
tech.root: debugger
ms.assetid: E6510000-E390-4631-9D47-5A57AB845EF6
ms.date: 05/03/2018
ms.keywords: AddBuffer, AddBuffer method [Windows Debugging], AddBuffer method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],AddBuffer method, IDebugFailureAnalysis2.AddBuffer, IDebugFailureAnalysis2::AddBuffer, debugger.idebugfailureanalysis2_addbuffer, extsfns/IDebugFailureAnalysis2::AddBuffer
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
-	IDebugFailureAnalysis2.AddBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::AddBuffer


## -description


The <b>AddBuffer</b> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object, and writes the bytes from a specified buffer to the data block of the new FA entry.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param EntryType [in]

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_ENTRY_TYPE</a> enumeration. This parameter specifies the data type of the data in <i>Buf</i>.


### -param Buf [in]

A pointer to a buffer that contains the bytes to be written to the data block of the new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>.


### -param Size [in]

The size, in bytes, of the buffer pointed to by <i>Buf</i>.


## -returns



If this method succeeds, it returns a pointer to the new <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.




## -remarks



This method creates a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the tag specified by <i>Tag</i>, and it associates the tag with the data type specified by <i>EntryType</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983413">GetBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983423">SetBuffer</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

