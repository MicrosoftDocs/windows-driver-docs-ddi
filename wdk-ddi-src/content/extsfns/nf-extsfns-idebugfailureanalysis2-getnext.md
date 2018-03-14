---
UID: NF:extsfns.IDebugFailureAnalysis2.GetNext
title: IDebugFailureAnalysis2::GetNext method
author: windows-driver-content
description: The GetNext method searches a DebugFailureAnalysis object for the next FA entry, after a given FA entry, that satisfies conditions specified by the Tag and TagMask parameters.
old-location: debugger\idebugfailureanalysis2_getnext.htm
old-project: debugger
ms.assetid: 935E4BAD-2B4E-44DD-8AE6-A0FD1FE9F2BF
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetNext method [Windows Debugging], GetNext method [Windows Debugging], IDebugFailureAnalysis2 interface, GetNext,IDebugFailureAnalysis2.GetNext, IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], GetNext method, IDebugFailureAnalysis2::GetNext, debugger.idebugfailureanalysis2_getnext, extsfns/IDebugFailureAnalysis2::GetNext
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
-	IDebugFailureAnalysis2.GetNext
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::GetNext method


## -description


   The <b>GetNext</b> method searches a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object for the next <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after a given FA entry, that satisfies conditions specified by the <i>Tag</i> and <i>TagMask</i> parameters.


## -syntax


````
PFA_ENTRY GetNext(
  [in] PFA_ENTRY Entry,
  [in] FA_TAG    Tag,
  [in] FA_TAG    TagMask
);
````


## -parameters




### -param Entry [in]

A pointer to an <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure. The search starts after this <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>. If this parameter is <b>NULL</b>, the starts at the beginning of the collection of FA entries.


### -param Tag [in]

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param TagMask [in]

A mask that restricts the search to a subset of all possible tags. See Remarks. To search all possible tags, set this parameter to <b>DEBUG_FLR_MASK_ALL</b>.


## -returns



If the <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object has an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after the given entry, that satisfies the conditions, this method returns a pointer to the <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure. Otherwise, this method returns <b>NULL</b>.




## -remarks



This method searches for an <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure that satisfies this condition:

entry-&gt;Tag &amp; <i>TagMask</i> == <i>Tag</i>

Tags are defined in extsfns.h as values of the <a href="..\extsfns\ne-extsfns-_debug_flr_param_type.md">DEBUG_FLR_PARAM_TYPE</a> enumeration, which is also called the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration. The tags are arranged in groups so that you can use <i>TagMask</i> to search within a particular group. For example there is a group of tags related to pool errors. The numerical values assigned to the tags in this group are in the range 0x400, 0x401 ... 0x406. Every <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> that has a tag in this group satisfies the following condition:

<code>entry-&gt;Tag &amp; 0xFFFFFF00 == 0x400</code>

The following code snippet shows a portion of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>...
// Pool
DEBUG_FLR_POOL_ADDRESS = 0x400,
DEBUG_FLR_SPECIAL_POOL_CORRUPTION_TYPE,
DEBUG_FLR_CORRUPTING_POOL_ADDRESS,
DEBUG_FLR_CORRUPTING_POOL_TAG,
DEBUG_FLR_FREED_POOL_TAG,
DEBUG_FLR_LEAKED_SESSION_POOL_TAG,
DEBUG_FLR_CLIENT_DRIVER,

// Filesystem
DEBUG_FLR_FILE_ID = 0x500,
DEBUG_FLR_FILE_LINE,
...</pre>
</td>
</tr>
</table></span></div>

#### Examples

<b>Example 1</b>

The following example shows how to find all failure analysis entries that have a tag equal to <b>DEBUG_FLR_MANAGED_EXCEPTION_OBJECT</b>. Assume <code>pAnalysis</code> is a pointer to an <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a> interface.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>FA_ENTRY entry = pAnalysis-&gt;Get(DEBUG_FLR_MANAGED_EXCEPTION_OBJECT);

while(NULL != entry)
{
   // Do something with the entry.

   entry = pAnalysis-&gt;GetNext(DEBUG_FLR_MANAGED_EXCEPTION_OBJECT, DEBUG_FLR_MASK_ALL);
}</pre>
</td>
</tr>
</table></span></div>
<b>Example 2</b>

The following example shows how to find all FA entries that have tags in the Pool group. Recall the tags in the Pool group have values in the range 0x400, 0x401, ... 0x406. Assume <code>pAnalysis</code> is a pointer to an <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a> interface.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>FA_ENTRY entry = pAnalysis-&gt;GetNext(NULL, (FA_TAG)0x400, (FA_TAG)0xFFFFFF00);

while(NULL != entry)
{
   // Do something with the entry.

   entry = pAnalysis-&gt;GetNext(entry, (FA_TAG)0x400, (FA_TAG)0xFFFFFF00);
}</pre>
</td>
</tr>
</table></span></div>
<b>Example 3</b>

You can create your own custom tags in the range 0xA0000001 through 0xAFFFFFFF.

The following example shows how to find all failure analysis entries that have custom tags. In other words, the code finds all entries with tags that satisfy this condition:

<code>entry-&gt;Tag &amp; 0xF0000000 == 0xA0000000</code>

Entries that have tags 0xA0000001, 0xA0000002, ... 0xAFFFFFF satisfy the condition. 

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>
FA_ENTRY entry = pAnalysis-&gt;GetNext(NULL, (FA_TAG)0xA0000000, (FA_TAG)0xF0000000);

while(NULL != entry)
{
   // Do something with the Entry

   entry = pAnalysis-&gt;GetNext(entry, (FA_TAG)0xA0000000, (FA_TAG)0xF0000000);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983411">Get</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983422">NextEntry</a>



<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>



 

 


