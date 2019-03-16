---
UID: NF:extsfns.IDebugFAEntryTags.GetProperties
title: IDebugFAEntryTags::GetProperties (extsfns.h)
description: The GetProperties method gets the name or description (or both) of a tag in a DebugFailureAnalysisTags object.
old-location: debugger\idebugfaentrytags_getproperties.htm
tech.root: debugger
ms.assetid: 140EAE7D-E349-4096-8578-6CF011C1FBA7
ms.date: 05/03/2018
ms.keywords: GetProperties, GetProperties method [Windows Debugging], GetProperties method [Windows Debugging],IDebugFAEntryTags interface, IDebugFAEntryTags interface [Windows Debugging],GetProperties method, IDebugFAEntryTags.GetProperties, IDebugFAEntryTags::GetProperties, debugger.idebugfaentrytags_getproperties, extsfns/IDebugFAEntryTags::GetProperties
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- extsfns.h
api_name:
- IDebugFAEntryTags.GetProperties
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugFAEntryTags::GetProperties


## -description


The <b>GetProperties</b> method gets the name or description (or both) of a tag in a <a href="https://msdn.microsoft.com/B52DFB0E-0035-40C2-B2F5-5E16B16931C2">DebugFailureAnalysisTags</a> object.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration. This method gets the name or description (or both) of this tag.


### -param Name [out]

A pointer to a buffer that receives a null-terminated string that is the name of the tag. If <i>NameSize</i> is less than the length of the tag's name, this method copies only <i>NameSize</i> bytes, including the <b>NULL</b> terminator, to this buffer.


### -param NameSize [in, out]

On input, this parameter, specifies the size, in bytes, of the buffer pointed to by <i>Name</i>. On output, this parameter receives the size, in bytes, of the name of the tag. If the tag has no name, this parameter receives a value of 0.

<div class="alert"><b>Note</b>  If <i>Name</i> is NULL, this parameter receives no information. You should either set both <i>Name</i> and <i>NameSize</i> to non-NULL values or set them both to <b>NULL</b>.</div>
<div> </div>

### -param Description [out]

A pointer to a buffer that receives a null-terminated string that is the description of the tag. If <i>DescSize</i> is less than the length of the tag's description, this method copies only <i>DescSize</i> bytes, including the <b>NULL</b> terminator, to this buffer.


### -param DescSize [in, out]

On input, this parameter, specifies the size, in bytes, of the buffer pointed to by <i>Description</i>. On output, this parameter receives the size, in bytes, of the description of the tag. If the tag has no description, this parameter receives a value of 0.

<div class="alert"><b>Note</b>  If <i>Description</i> is NULL, this parameter receives no information. You should either set both <i>Description</i> and <i>DescSize</i> to non-NULL values or set them both to <b>NULL</b>.</div>
<div> </div>

### -param Flags [out]

Reserved. Set this parameter to NULL.


## -returns



The <b>HRESULT</b> values returned by this method are defined in winerror.h and strsafe.h. The values returned by this method include, but are not limited to the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
This method successfully retrieved the requested name or description  (or both), and no truncation of the requested string or strings was required.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STRSAFE_E_INSUFFICIENT_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
This method retrieved the requested name or description (or both), but the name or description was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STRSAFE_E_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">
The caller passed at least one invalid parameter.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983404">IDebugFAEntryTags</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj991815">SetProperties</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

