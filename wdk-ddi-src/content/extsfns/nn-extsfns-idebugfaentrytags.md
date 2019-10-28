---
UID: NN:extsfns.IDebugFAEntryTags
title: IDebugFAEntryTags (extsfns.h)
description: When the !analyze debugger command runs, the analysis engine can load and run extension analysis plug-ins.
old-location: debugger\idebugfaentrytags.htm
tech.root: debugger
ms.assetid: B52DFB0E-0035-40C2-B2F5-5E16B16931C2
ms.date: 05/03/2018
ms.keywords: IDebugFAEntryTags, IDebugFAEntryTags interface [Windows Debugging], IDebugFAEntryTags interface [Windows Debugging],described, debugger.idebugfaentrytags, extsfns/IDebugFAEntryTags
ms.topic: interface
f1_keywords:
 - "extsfns/IDebugFAEntryTags"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- extsfns.h
api_name:
- IDebugFAEntryTags
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFAEntryTags interface


## -description


 When the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-analyze">!analyze</a> debugger command runs, the analysis engine
   can load and run extension analysis plug-ins. The analysis engine creates a 
	<b>DebugFailureAnalysisTags</b> object to organize information 
	about the tags that are used by a particular analysis session.

An extension analysis plug-in accesses a
	 <b>DebugFailureAnalysisTags</b> object through an 
	 <b>IDebugFAEntryTags</b> interface. 
	 For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Failure Analysis Entries, Tags, and Data Types</a>

The <b>IDebugFAEntryTags</b>
 interface is not a COM interface;removremoproc that is, it does not inherit from <b>IUnknown</b>

To get an <b>IDebugFAEntryTags</b> interface,
  call the <b>GetDebugFATagControl</b> method of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a> 
  interface.


<h2><a id="in_this_section"></a>In this section</h2>
<table>
<tr>
<th>Topic</th>
<th>Description</th>
</tr>
<tr>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-getproperties">GetProperties method</a>


</td>
<td>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-getproperties">GetProperties</a> method gets the name or description (or both) of a tag in a DebugFailureAnalysisTags object.

</td>
</tr>
<tr>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettagbyname">GetTagByName method</a>


</td>
<td>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettagbyname">GetTagByName</a> method searches for a tag that has a specified name.

</td>
</tr>
<tr>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType method</a>


</td>
<td>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a> method gets the data type that is associated with a tag in a DebugFailureAnalysisTags object.

</td>
</tr>
<tr>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-isvalidtagtoset">IsValidTagToSet method</a>


</td>
<td>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-isvalidtagtoset">IsValidTagToSet</a> method determines whether it is OK to set the data of a specified tag.

</td>
</tr>
<tr>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-setproperties">SetProperties method</a>


</td>
<td>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-setproperties">SetProperties</a> method sets the name or description (or both) of a tag in a DebugFailureAnalysisTags object. 

</td>
</tr>
<tr>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-settype">SetType method</a>


</td>
<td>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-settype">SetType</a> method sets the data type that is associated with a tag in a DebugFailureAnalysisTags object.

</td>
</tr>
</table>
 



