---
UID: NF:extsfns.IDebugFailureAnalysis2.SetUlong64
title: IDebugFailureAnalysis2::SetUlong64
description: The SetUlong64 method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified ULONG64 value.
old-location: debugger\idebugfailureanalysis2_setulong64.htm
tech.root: debugger
ms.assetid: C4F293C1-D52C-4584-A8CE-98F14F3309DD
ms.date: 05/03/2018
ms.keywords: IDebugFailureAnalysis2 interface [Windows Debugging],SetUlong64 method, IDebugFailureAnalysis2.SetUlong64, IDebugFailureAnalysis2::SetUlong64, SetUlong64, SetUlong64 method [Windows Debugging], SetUlong64 method [Windows Debugging],IDebugFailureAnalysis2 interface, debugger.idebugfailureanalysis2_setextensionulong64, debugger.idebugfailureanalysis2_setulong64, extsfns/IDebugFailureAnalysis2::SetUlong64
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
-	IDebugFailureAnalysis2.SetUlong64
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::SetUlong64


## -description


The <b>SetUlong64</b> method searches a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified <b>ULONG64</b> value.  If this method does not find an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has the specified tag, it creates a new FA entry with that tag and sets the data block of the new FA entry to the specified <b>ULONG64</b> value.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param Value [in]

The <b>ULONG64</b> value to be written to the data block of the new or existing <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>.


## -returns



If this method succeeds, it returns a pointer to the new or existing <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.




## -remarks



If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it checks to see whether the data type associated with that tag is <b>DEBUG_FA_ENTRY_ULONG64</b>, <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b>, or <b>DEBUG_FA_ENTRY_POINTER</b>. If the data type associated with the tag does not have one of those three values, this method returns NULL and does not overwrite the entry's data block.

If this method does not find an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it creates a new FA entry with that tag, and it associates the tag with the data type  <b>DEBUG_FA_ENTRY_ULONG64</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983410">AddUlong64</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983421">GetUlong64</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

