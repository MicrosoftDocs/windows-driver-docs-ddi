---
UID: NF:extsfns.IDebugFAEntryTags.GetTagByName
title: IDebugFAEntryTags::GetTagByName method
author: windows-driver-content
description: The GetTagByName method searches for a tag that has a specified name.
old-location: debugger\idebugfaentrytags_gettagbyname.htm
old-project: debugger
ms.assetid: 3EA8FE2A-85CE-4C81-81EB-F08028F0F822
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetTagByName method [Windows Debugging], GetTagByName method [Windows Debugging], IDebugFAEntryTags interface, GetTagByName,IDebugFAEntryTags.GetTagByName, IDebugFAEntryTags, IDebugFAEntryTags interface [Windows Debugging], GetTagByName method, IDebugFAEntryTags::GetTagByName, debugger.idebugfaentrytags_gettagbyname, extsfns/IDebugFAEntryTags::GetTagByName
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
-	IDebugFAEntryTags.GetTagByName
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFAEntryTags::GetTagByName method


## -description


The <b>GetTagByName</b> method searches for a tag that has a specified name.


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



A <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object has a collection of <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entries</a>, each of which has a tag. A <b>DebugFailureAnalysis</b> object is associated with a <a href="https://msdn.microsoft.com/B52DFB0E-0035-40C2-B2F5-5E16B16931C2">DebugFailureAnalysisTags</a>, which contains a collection of tag properties. Also, the analysis engine has a global tag table. For more information, see <a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Failure Analysis Entries, Tags, and Data Types</a>.

If you specify a <i>PluginId</i>, this method does the following:

<ul>
<li>In the  <a href="https://msdn.microsoft.com/B52DFB0E-0035-40C2-B2F5-5E16B16931C2">DebugFailureAnalysisTags</a> object, search the collection of tag properties for a tag whose name matches <i>TagName</i> and whose plug-in id matches the <i>PluginId</i>. Note that this limits the search to custom tags created by the analysis extension plug-in identified by <i>PluginId</i>. If a match is found, return the tag in the <i>Tag</i> output parameter.</li>
<li>If a match is not found in the <a href="https://msdn.microsoft.com/B52DFB0E-0035-40C2-B2F5-5E16B16931C2">DebugFailureAnalysisTags</a> object, search the global tag table for a tag whose name matches <i>TagName</i>. If a matching name is found, add the found tag to the <b>DebugFailureAnalysisTags</b> collection of tag properties, and return the tag in the <i>Tag</i> output parameter.</li>
<li>If a match is not found in the global tag table, write nothing to the <i>Tag</i> output parameter, and return a failure code.</li>
</ul>
If you call this method from an analysis extension plug-in, and you set <i>PluginId</i> to <b>NULL</b>, this method uses the plug-in identifier of the current plug-in. Then it behaves the same way that it does when a non-NULL <i>PluginId</i> is specified.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983428">Metadata Files for Analysis Extension Plug-ins</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFAEntryTags::GetTagByName method%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

