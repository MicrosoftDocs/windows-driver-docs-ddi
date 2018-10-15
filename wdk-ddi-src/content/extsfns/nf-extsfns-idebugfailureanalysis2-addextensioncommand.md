---
UID: NF:extsfns.IDebugFailureAnalysis2.AddExtensionCommand
title: IDebugFailureAnalysis2::AddExtensionCommand
author: windows-driver-content
description: The AddExtensionCommand method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified debugger command.
old-location: debugger\idebugfailureanalysis2_addextensioncommand.htm
tech.root: debugger
ms.assetid: 370A4EBA-80BF-46B2-8F52-9F04A4EC98D7
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: AddExtensionCommand, AddExtensionCommand method [Windows Debugging], AddExtensionCommand method [Windows Debugging],IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging],AddExtensionCommand method, IDebugFailureAnalysis2.AddExtensionCommand, IDebugFailureAnalysis2::AddExtensionCommand, debugger.idebugfailureanalysis2_addextensioncommand, extsfns/IDebugFailureAnalysis2::AddExtensionCommand
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
-	IDebugFailureAnalysis2.AddString
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2::AddExtensionCommand


## -description


The <b>AddExtensionCommand</b> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object and sets the data block of the FA entry to a specified debugger command.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration. The data type associated with this tag must be <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b> or <b>DEBUG_FA_ENTRY_ANSI_STRING</b>.


### -param Extension






#### - Str [in]

A pointer to a null-terminated ANSI string that is the debugger command. An example of debugger command is "!analyze -v".


## -returns



If this method succeeds, it returns a returns a pointer to the new <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure. If this method fails, it returns <b>NULL</b>.





## -remarks



This method sets the <b>DataSize</b> member of the new <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure to the length, in bytes, of the extension command including the <b>NULL</b> terminator.

Each tag is associated with one of the data types in the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991809">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a> interface.

To get a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a> interface, call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983414">GetDebugFATagControl</a> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a> interface.

[sperry] Note to Self: If the given tag has not already had its data type fixed, this method sets and fixes the data type for the tag. That would be the case if the DebugFailureAnalysis object does not yet have an FA entry with this tag. But if the DebugFailureAnalysis object already has an FA entry with this tag, then the data type of the tag is fixed. This method creates a new FA entry with the same tag. Now what if the data type that we're trying to write into the new data buffer does not match the data type that has been fixed for this tag. Then we see whether it's OK to cast from the fixed data type to the type we want to write.

It's OK to cast among ULONG64, POINTER, and InstructionOffset. It's OK to cast among String and ExtensionCommand. ULONG can only be ULONG. STRINGs can only be STRINGs.

Question: When does the data type of a tag get fixed? Is it when the first FA entry with that tag is created?

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef struct _FA_TAG_PROPS
{
    FA_TAG Tag;
    FA_ENTRY_TYPE Type;
    ULONG Fixed:1;
    ULONG NameAllocated:1;
    ULONG DescriptionAllocated:1;
    PCSTR Name;
    PCSTR Description;
    AnalysisPlugIn *Plugin;
} FA_TAG_PROPS, *PFA_TAG_PROPS;</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983424">SetExtensionCommand</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

