---
UID: NF:extsfns.IDebugFailureAnalysis2.AddString
title: IDebugFailureAnalysis2::AddString method
author: windows-driver-content
description: The AddString method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified string.
old-location: debugger\idebugfailureanalysis2_addstring.htm
old-project: debugger
ms.assetid: 98023A9B-9091-4C0D-ADE0-978816E8F762
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AddString method [Windows Debugging], AddString method [Windows Debugging], IDebugFailureAnalysis2 interface, AddString,IDebugFailureAnalysis2.AddString, IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], AddString method, IDebugFailureAnalysis2::AddString, debugger.idebugfailureanalysis2_addstring, extsfns/IDebugFailureAnalysis2::AddString
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
-	IDebugFailureAnalysis2.AddString
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::AddString method


## -description


The <b>AddString</b> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object and sets the data block of the FA entry to a specified string.


## -syntax


````
HRESULT AddString(
       FA_TAG Tag,
  [in] PSTR   Str
);
````


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration. The data type associated with this tag must be <b>DEBUG_FA_ENTRY_ANSI_STRING</b>.


### -param Str [in]

A pointer to a null-terminated ANSI string to be written to the data block of the new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>.


## -returns



If this method succeeds, it returns a returns a pointer to the new <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure. If this method fails, it returns <b>NULL</b>.





## -remarks



This method sets the <b>DataSize</b> member of the new <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure to the length, in bytes, of the string including the <b>NULL</b> terminator.

Each tag is associated with one of the data types in the <a href="..\extsfns\ne-extsfns-_fa_entry_type.md">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a> method of the <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a> interface.

To get a pointer to an <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a> interface, call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983414">GetDebugFATagControl</a> method of the <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a> interface. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983419">GetString</a>



<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>



<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>



<a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983427">SetString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::AddString method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

