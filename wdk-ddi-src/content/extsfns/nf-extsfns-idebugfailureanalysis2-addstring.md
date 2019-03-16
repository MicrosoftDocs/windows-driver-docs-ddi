---
UID: NF:extsfns.IDebugFailureAnalysis2.AddString
title: IDebugFailureAnalysis2::AddString (extsfns.h)
description: The AddString method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified string.
old-location: debugger\idebugfailureanalysis2_addstring.htm
tech.root: debugger
ms.assetid: 98023A9B-9091-4C0D-ADE0-978816E8F762
ms.date: 05/03/2018
ms.keywords: AddString, AddString method [Windows Debugging], AddString method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],AddString method, IDebugFailureAnalysis2.AddString, IDebugFailureAnalysis2::AddString, debugger.idebugfailureanalysis2_addstring, extsfns/IDebugFailureAnalysis2::AddString
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- extsfns.h
api_name:
- IDebugFailureAnalysis2.AddString
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::AddString


## -description


The <b>AddString</b> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object and sets the data block of the FA entry to a specified string.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration. The data type associated with this tag must be <b>DEBUG_FA_ENTRY_ANSI_STRING</b>.


### -param Str [in]

A pointer to a null-terminated ANSI string to be written to the data block of the new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>.


## -returns



If this method succeeds, it returns a returns a pointer to the new <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure. If this method fails, it returns <b>NULL</b>.





## -remarks



This method sets the <b>DataSize</b> member of the new <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure to the length, in bytes, of the string including the <b>NULL</b> terminator.

Each tag is associated with one of the data types in the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991809">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a> interface.

To get a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a> interface, call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983414">GetDebugFATagControl</a> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a> interface. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983419">GetString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983427">SetString</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

