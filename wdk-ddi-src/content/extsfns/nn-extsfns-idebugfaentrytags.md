---
UID: NN:extsfns.IDebugFAEntryTags
title: IDebugFAEntryTags
author: windows-driver-content
description: When the !analyze debugger command runs, the analysis engine can load and run extension analysis plug-ins.
old-location: debugger\idebugfaentrytags.htm
tech.root: debugger
ms.assetid: B52DFB0E-0035-40C2-B2F5-5E16B16931C2
ms.date: 5/3/2018
ms.keywords: IDebugFAEntryTags, IDebugFAEntryTags interface [Windows Debugging], IDebugFAEntryTags interface [Windows Debugging],described, debugger.idebugfaentrytags, extsfns/IDebugFAEntryTags
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
-	IDebugFAEntryTags
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFAEntryTags interface


## -description


 When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562112">!analyze</a> debugger command runs, the analysis engine
   can load and run extension analysis plug-ins. The analysis engine creates a 
	<b>DebugFailureAnalysisTags</b> object to organize information 
	about the tags that are used by a particular analysis session.

An extension analysis plug-in accesses a
	 <b>DebugFailureAnalysisTags</b> object through an 
	 <b>IDebugFAEntryTags</b> interface. 
	 For more information, see <a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Failure Analysis Entries, Tags, and Data Types</a>

The <b>IDebugFAEntryTags</b>
 interface is not a COM interface;removremoproc that is, it does not inherit from <b>IUnknown</b>

To get an <b>IDebugFAEntryTags</b> interface,
  call the <b>GetDebugFATagControl</b> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a> 
  interface.


<h2><a id="in_this_section"></a>In this section</h2>
<table>
<tr>
<th>Topic</th>
<th>Description</th>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/140EAE7D-E349-4096-8578-6CF011C1FBA7">GetProperties method</a>


</td>
<td>
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj991811">GetProperties</a> method gets the name or description (or both) of a tag in a DebugFailureAnalysisTags object.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/3EA8FE2A-85CE-4C81-81EB-F08028F0F822">GetTagByName method</a>


</td>
<td>
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj991812">GetTagByName</a> method searches for a tag that has a specified name.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/CE43711F-E17B-4234-A885-4FE04EA53903">GetType method</a>


</td>
<td>
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a> method gets the data type that is associated with a tag in a DebugFailureAnalysisTags object.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/83B5C54F-182B-4D2F-8ED2-7A0B529F1D2E">IsValidTagToSet method</a>


</td>
<td>
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj991814">IsValidTagToSet</a> method determines whether it is OK to set the data of a specified tag.

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/EEBD3291-4DFC-4503-9F5A-49591FE09680">SetProperties method</a>


</td>
<td>
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj991815">SetProperties</a> method sets the name or description (or both) of a tag in a DebugFailureAnalysisTags object. 

</td>
</tr>
<tr>
<td>

<a href="https://msdn.microsoft.com/F507864B-B20C-4F71-B068-802780243106">SetType method</a>


</td>
<td>
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj991816">SetType</a> method sets the data type that is associated with a tag in a DebugFailureAnalysisTags object.

</td>
</tr>
</table>
 



