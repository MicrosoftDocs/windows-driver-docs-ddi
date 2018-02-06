---
UID: NN:extsfns.IDebugFailureAnalysis2
title: IDebugFailureAnalysis2
author: windows-driver-content
description: When the !analyze debugger command runs, the analysis engine can load and run extension analysis plug-ins.
old-location: debugger\idebugfailureanalysis2.htm
old-project: debugger
ms.assetid: 0B44FCB9-D23F-4630-9F9A-FBAD46712B14
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugfailureanalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], IDebugFailureAnalysis2 interface [Windows Debugging], described, IDebugFailureAnalysis2, extsfns/IDebugFailureAnalysis2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: extsfns.h
req.include-header: 
req.target-type: Windows
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
-	IDebugFailureAnalysis2
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2 interface


## -description


When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562112">!analyze</a> debugger command runs, the analysis engine can load and run extension analysis plug-ins. The analysis engine creates a <i>DebugFailureAnalysis object</i> to organize data that is related to a particular analysis session.

 An extension analysis plug-in can access a DebugFailureAnalysis object through an <b>IDebugFailureAnalysis2</b> interface. The plug-in can inspect, alter, and enhance the information created by the default analysis. For more information, see <a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>.


## -members

The <b>IDebugFailureAnalysis2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983406">AddBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983406">AddBuffer</a> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <b>DebugFailureAnalysis</b> object, and writes the bytes from a specified buffer to the data block of the new FA entry.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983407">AddExtensionCommand</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983407">AddExtensionCommand</a> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <b>DebugFailureAnalysis</b> object and sets the data block of the FA entry to a specified debugger command.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406612">AddString</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406612">AddString</a> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <b>DebugFailureAnalysis</b> object and sets the data block of the FA entry to a specified string.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983409">AddUlong</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983409">AddUlong</a> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>  to a <b>DebugFailureAnalysis</b> object and sets the data block of the FA entry to a specified <b>ULONG</b> value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983410">AddUlong64</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983410">AddUlong64</a> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>  to a <b>DebugFailureAnalysis</b> object and sets the data block of the FA entry to a specified 64-bit value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983411">Get</a>
</td>
<td align="left" width="63%">
   The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983411">Get</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983413">GetBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983413">GetBuffer</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the entry's data block.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983414">GetDebugFATagControl</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983414">GetDebugFATagControl</a> method gets a pointer to an <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a> interface, which provides access to the tags in a DebugFailureAnalysisTags object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983415">GetFailureClass</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983415">GetFailureClass</a> method gets the failure class of a <b>DebugFailureAnalysis</b> object. The failure class indicates whether the debugging session  that created the <b>DebugFailureAnalysis</b> object is a kernel mode session or a user mode session.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983416">GetFailureCode</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983416">GetFailureCode</a> method gets the bug check code or exception code of a <b>DebugFailureAnalysis</b> object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983417">GetFailureType</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983417">GetFailureType</a> method gets the failure type of a <b>DebugFailureAnalysis</b> object. The failure type indicates whether the code being analyzed was running in kernel mode or user mode.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983418">GetNext</a>
</td>
<td align="left" width="63%">
   The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983418">GetNext</a> method searches a <b>DebugFailureAnalysis</b> object for the next <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after a given FA entry, that satisfies conditions specified by the <i>Tag</i> and <i>TagMask</i> parameters.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983419">GetString</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983419">GetString</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the ANSI string value from the entry's data block.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983420">GetUlong</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983420">GetUlong</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the <b>ULONG</b> value from the entry's data block.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983421">GetUlong64</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983421">GetUlong64</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the <b>ULONG64</b> value from the entry's data block.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983422">NextEntry</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983422">NextEntry</a> method gets the next <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after a given FA entry, in a <b>DebugFailureAnalysis</b> object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983423">SetBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983423">SetBuffer</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it overwrites the data block of the FA entry with the bytes in a specified buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983424">SetExtensionCommand</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983424">SetExtensionCommand</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified extension command string.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983427">SetString</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983427">SetString</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified string value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983425">SetUlong</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983425">SetUlong</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified <b>ULONG</b> value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983426">SetUlong64</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983426">SetUlong64</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified <b>ULONG64</b> value.

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983406">AddBuffer</a> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <b>DebugFailureAnalysis</b> object, and writes the bytes from a specified buffer to the data block of the new FA entry.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983407">AddExtensionCommand</a> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <b>DebugFailureAnalysis</b> object and sets the data block of the FA entry to a specified debugger command.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406612">AddString</a> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> to a <b>DebugFailureAnalysis</b> object and sets the data block of the FA entry to a specified string.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983409">AddUlong</a> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>  to a <b>DebugFailureAnalysis</b> object and sets the data block of the FA entry to a specified <b>ULONG</b> value.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983410">AddUlong64</a> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>  to a <b>DebugFailureAnalysis</b> object and sets the data block of the FA entry to a specified 64-bit value.

   The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983411">Get</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983413">GetBuffer</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the entry's data block.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983414">GetDebugFATagControl</a> method gets a pointer to an <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a> interface, which provides access to the tags in a DebugFailureAnalysisTags object.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983415">GetFailureClass</a> method gets the failure class of a <b>DebugFailureAnalysis</b> object. The failure class indicates whether the debugging session  that created the <b>DebugFailureAnalysis</b> object is a kernel mode session or a user mode session.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983416">GetFailureCode</a> method gets the bug check code or exception code of a <b>DebugFailureAnalysis</b> object.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983417">GetFailureType</a> method gets the failure type of a <b>DebugFailureAnalysis</b> object. The failure type indicates whether the code being analyzed was running in kernel mode or user mode.

   The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983418">GetNext</a> method searches a <b>DebugFailureAnalysis</b> object for the next <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after a given FA entry, that satisfies conditions specified by the <i>Tag</i> and <i>TagMask</i> parameters.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983419">GetString</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the ANSI string value from the entry's data block.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983420">GetUlong</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the <b>ULONG</b> value from the entry's data block.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983421">GetUlong64</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the <b>ULONG64</b> value from the entry's data block.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983422">NextEntry</a> method gets the next <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after a given FA entry, in a <b>DebugFailureAnalysis</b> object.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983423">SetBuffer</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it overwrites the data block of the FA entry with the bytes in a specified buffer.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983424">SetExtensionCommand</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified extension command string.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983427">SetString</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified string value.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983425">SetUlong</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified <b>ULONG</b> value.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983426">SetUlong64</a> method searches a <b>DebugFailureAnalysis</b> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified <b>ULONG64</b> value.

 


## -see-also

<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562112">!analyze</a>

<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2 interface%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

