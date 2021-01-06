---
UID: NF:extsfns.IDebugFAEntryTags.GetTagByName
title: IDebugFAEntryTags::GetTagByName (extsfns.h)
description: The GetTagByName method searches for a tag that has a specified name.
old-location: debugger\idebugfaentrytags_gettagbyname.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugFAEntryTags::GetTagByName"]
ms.keywords: GetTagByName, GetTagByName method [Windows Debugging], GetTagByName method [Windows Debugging],IDebugFAEntryTags interface, IDebugFAEntryTags interface [Windows Debugging],GetTagByName method, IDebugFAEntryTags.GetTagByName, IDebugFAEntryTags::GetTagByName, debugger.idebugfaentrytags_gettagbyname, extsfns/IDebugFAEntryTags::GetTagByName
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugFAEntryTags::GetTagByName
 - extsfns/IDebugFAEntryTags::GetTagByName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFAEntryTags.GetTagByName
---

# IDebugFAEntryTags::GetTagByName


## -description

The <b>GetTagByName</b> method searches for a tag that has a specified name.

## -parameters

### -param PluginId 

[in]
A pointer to a null-terminated string that specifies the identifier of an analysis extension plug-in. This parameter can be <b>NULL</b>.

### -param TagName 

[in]
A pointer to a null-terminated string that specifies the name to search for.

### -param Tag 

[out]
A pointer to a variable that receives either a value in the <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration or the value of a custom tag. If this method does not find a tag that has the specified name, nothing is written to this parameter.

## -returns

If this method finds a tag that has the specified name, it returns <b>S_OK</b>. Otherwise it returns a failure code.

## -remarks

A <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object has a collection of <a href="/windows-hardware/drivers/debugger/failure-analysis-entries">FA entries</a>, each of which has a tag. A <b>DebugFailureAnalysis</b> object is associated with a <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">DebugFailureAnalysisTags</a>, which contains a collection of tag properties. Also, the analysis engine has a global tag table. For more information, see <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Failure Analysis Entries, Tags, and Data Types</a>.

If you specify a <i>PluginId</i>, this method does the following:

<ul>
<li>In the  <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">DebugFailureAnalysisTags</a> object, search the collection of tag properties for a tag whose name matches <i>TagName</i> and whose plug-in id matches the <i>PluginId</i>. Note that this limits the search to custom tags created by the analysis extension plug-in identified by <i>PluginId</i>. If a match is found, return the tag in the <i>Tag</i> output parameter.</li>
<li>If a match is not found in the <a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">DebugFailureAnalysisTags</a> object, search the global tag table for a tag whose name matches <i>TagName</i>. If a matching name is found, add the found tag to the <b>DebugFailureAnalysisTags</b> collection of tag properties, and return the tag in the <i>Tag</i> output parameter.</li>
<li>If a match is not found in the global tag table, write nothing to the <i>Tag</i> output parameter, and return a failure code.</li>
</ul>
If you call this method from an analysis extension plug-in, and you set <i>PluginId</i> to <b>NULL</b>, this method uses the plug-in identifier of the current plug-in. Then it behaves the same way that it does when a non-NULL <i>PluginId</i> is specified.

## -see-also

<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfaentrytags">IDebugFAEntryTags</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="/windows-hardware/drivers/debugger/metadata-files-for-analysis-extensions">Metadata Files for Analysis Extension Plug-ins</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
