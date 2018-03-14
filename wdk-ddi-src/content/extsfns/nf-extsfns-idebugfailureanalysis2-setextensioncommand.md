---
UID: NF:extsfns.IDebugFailureAnalysis2.SetExtensionCommand
title: IDebugFailureAnalysis2::SetExtensionCommand method
author: windows-driver-content
description: The SetExtensionCommand method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag.
old-location: debugger\idebugfailureanalysis2_setextensioncommand.htm
old-project: debugger
ms.assetid: 741B3D1F-FA7B-4260-AD0C-461D76605CBA
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], SetExtensionCommand method, IDebugFailureAnalysis2::SetExtensionCommand, SetExtensionCommand method [Windows Debugging], SetExtensionCommand method [Windows Debugging], IDebugFailureAnalysis2 interface, SetExtensionCommand,IDebugFailureAnalysis2.SetExtensionCommand, debugger.idebugfailureanalysis2_setextensioncommand, extsfns/IDebugFailureAnalysis2::SetExtensionCommand
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
-	IDebugFailureAnalysis2.SetExtensionCommand
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::SetExtensionCommand method


## -description


The <b>SetExtensionCommand</b> method searches a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified extension command string. If this method does not find an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has the specified tag, it creates a new FA entry with that tag and sets the data block of the new FA entry to the specified extension command string.


## -syntax


````
FA_ENTRY SetExtensionCommand(
   FA_TAG Tag,
   PCSTR  Extension
);
````


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param Extension

A pointer to a null-terminated string that is the extension command. An example of an extension command is "!analyze -v".


## -returns



If this method succeeds, it returns a pointer to the new or existing <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.




## -remarks



If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it checks to see whether the data type associated with that tag is <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b> or <b>DEBUG_FA_ENTRY_ANSI_STRING</b>. If the data type associated with the tag does not have one of those two values, this method returns <b>NULL</b> and does not overwrite the entry's data block.

If this method does not find an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it creates a new FA entry with that tag, and it associates the tag with the data type  <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b>. 




## -see-also

<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983407">AddExtensionCommand</a>



<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>



 

 


