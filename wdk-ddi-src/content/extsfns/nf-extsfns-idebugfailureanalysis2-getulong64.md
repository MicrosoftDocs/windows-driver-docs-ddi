---
UID: NF:extsfns.IDebugFailureAnalysis2.GetUlong64
title: IDebugFailureAnalysis2::GetUlong64
description: The GetUlong64 method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the ULONG64 value from the entry's data block.
old-location: debugger\idebugfailureanalysis2_getulong64.htm
tech.root: debugger
ms.assetid: C00C983A-92BA-4E4A-A5AB-918121D14B64
ms.date: 05/03/2018
ms.keywords: GetUlong64, GetUlong64 method [Windows Debugging], GetUlong64 method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],GetUlong64 method, IDebugFailureAnalysis2.GetUlong64, IDebugFailureAnalysis2::GetUlong64, debugger.idebugfailureanalysis2_getulong64, extsfns/IDebugFailureAnalysis2::GetUlong64
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
-	IDebugFailureAnalysis2.GetUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::GetUlong64


## -description


The <b>GetUlong64</b> method searches a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the <b>ULONG64</b> value from the entry's data block.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param Value [out]

A pointer to a <b>ULONG64</b> that receives the value from the entry's data block.


## -returns



If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, and if it succeeds in getting the data block, it returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.




## -remarks



If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it checks to see whether the <b>DataSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure is equal to the size of a <b>ULONG64</b>. If <b>DataSize</b> is not equal to the size of a <b>ULONG64</b>, this method returns <b>NULL</b> and does not get the data block.

Each tag that has already been used in a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object is associated with one of the data types in the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991809">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a> interface. To get a pointer to an IDebugFAEntryTags interface, call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983414">GetDebugFATagControl</a> method of the <b>IDebugFailureAnalysis2</b> interface.

The appropriate use of this method is get the data block from an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a data type of <b>DEBUG_FA_ENTRY_ULONG64</b> or <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b> or <b>DEBUG_FA_ENTRY_POINTER</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983410">AddUlong64</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983426">SetUlong64</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

