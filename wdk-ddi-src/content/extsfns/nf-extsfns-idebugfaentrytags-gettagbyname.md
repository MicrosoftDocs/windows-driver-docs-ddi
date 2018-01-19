---
UID: NF:extsfns.IDebugFAEntryTags.GetTagByName
title: IDebugFAEntryTags::GetTagByName method
author: windows-driver-content
description: The GetTagByName method searches for a tag that has a specified name.
old-location: debugger\idebugfaentrytags_gettagbyname.htm
old-project: debugger
ms.assetid: 3EA8FE2A-85CE-4C81-81EB-F08028F0F822
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugFAEntryTags, IDebugFAEntryTags::GetTagByName, GetTagByName
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
req.alt-api: IDebugFAEntryTags.GetTagByName
req.alt-loc: extsfns.h
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
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFAEntryTags::GetTagByName method



## -description
The <b>GetTagByName</b> method searches for a tag that has a specified name.



## -syntax

````
HRESULT GetTagByName(
  [in]  PCSTR   PluginId,
  [in]  PCSTR   TagName,
  [out] FA_TAG* Tag
);
````


## -parameters

### -param PluginId [in]

A pointer to a null-terminated string that specifies the identifier of an analysis extension plug-in. This parameter can be <b>NULL</b>.


### -param TagName [in]

A pointer to a null-terminated string that specifies the name to search for.


### -param Tag [out]

A pointer to a variable that receives either a value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration or the value of a custom tag. If this method does not find a tag that has the specified name, nothing is written to this parameter.


## -returns
If this method finds a tag that has the specified name, it returns <b>S_OK</b>. Otherwise it returns a failure code.


## -remarks
A <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object has a collection of <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entries</a>, each of which has a tag. A <b>DebugFailureAnalysis</b> object is associated with a <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">DebugFailureAnalysisTags</a>, which contains a collection of tag properties. Also, the analysis engine has a global tag table. For more information, see <a href="debugger.writing_an_analysis_extension_to_extend__analyze#failure_analysis_entries_tags_and_data_types#failure_analysis_entries_tags_and_data_types">Failure Analysis Entries, Tags, and Data Types</a>.

If you specify a <i>PluginId</i>, this method does the following:

If you call this method from an analysis extension plug-in, and you set <i>PluginId</i> to <b>NULL</b>, this method uses the plug-in identifier of the current plug-in. Then it behaves the same way that it does when a non-NULL <i>PluginId</i> is specified.


## -see-also
<dl>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a>
</dt>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983428">Metadata Files for Analysis Extension Plug-ins</a>
</dt>
<dt>
<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFAEntryTags::GetTagByName method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

