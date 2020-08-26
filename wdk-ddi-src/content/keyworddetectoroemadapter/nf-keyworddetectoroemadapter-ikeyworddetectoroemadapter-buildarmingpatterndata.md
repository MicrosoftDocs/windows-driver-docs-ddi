---
UID: NF:keyworddetectoroemadapter.IKeywordDetectorOemAdapter.BuildArmingPatternData
title: IKeywordDetectorOemAdapter::BuildArmingPatternData (keyworddetectoroemadapter.h)
description: The BuildArmingPatternData method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection.
old-location: audio\ikeyworddetectoroemadapter_buildarmingpatterndata.htm
tech.root: audio
ms.assetid: F74DC3C3-C182-4BBA-93C8-95A73C58CFEF
ms.date: 05/08/2018
keywords: ["IKeywordDetectorOemAdapter::BuildArmingPatternData"]
ms.keywords: BuildArmingPatternData, BuildArmingPatternData method [Audio Devices], BuildArmingPatternData method [Audio Devices],IKeywordDetectorOemAdapter interface, IKeywordDetectorOemAdapter interface [Audio Devices],BuildArmingPatternData method, IKeywordDetectorOemAdapter.BuildArmingPatternData, IKeywordDetectorOemAdapter::BuildArmingPatternData, audio.ikeyworddetectoroemadapter_buildarmingpatterndata, keyworddetectoroemadapter/IKeywordDetectorOemAdapter::BuildArmingPatternData
f1_keywords:
 - "keyworddetectoroemadapter/IKeywordDetectorOemAdapter.BuildArmingPatternData"
 - "IKeywordDetectorOemAdapter.BuildArmingPatternData"
req.header: keyworddetectoroemadapter.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: KeywordDetectorOemAdapter.idl
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
- KeywordDetectorOemAdapter.h
api_name:
- IKeywordDetectorOemAdapter.BuildArmingPatternData
targetos: Windows
req.typenames: 
---

# IKeywordDetectorOemAdapter::BuildArmingPatternData


## -description


The <b>BuildArmingPatternData</b> method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection.


## -parameters




### -param UserModelData 
[in]
A pointer to <b>IStream</b> bound to model data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/keyworddetectoroemadapter/ns-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0003">KEYWORDSELECTOR</a> values in the <i>KeywordSelectors</i> parameter.


### -param KeywordSelectors 
[in]
An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/keyworddetectoroemadapter/ns-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0003">KEYWORDSELECTOR</a> structures identifying the desired set of matches for the keyword detector to arm.


### -param NumKeywordSelectors 
[in]
The number of items in the <i>KeywordSelectors</i> array. Only one key word selector is supported and this field must be set to one.


### -param ppPatternData 
[out]
The pattern data for the operating system to pass to the audio driver. The OEMDLL allocates the memory calling <a href="https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc">CoTaskMemAlloc</a>. The operating system will free the memory by calling <a href="https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree">CoTaskMemFree</a>.


## -returns



This method can return one of these values.

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>S_OK</dt>
</dl>
</td>
<td width="60%">
The function exited successfully. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>E_POINTER</dt>
</dl>
</td>
<td width="60%">
 The <i>ModelData</i> pointer is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>E_INVALIDARG</dt>
</dl>
</td>
<td width="60%">
 The <i>KeywordId</i> or <i>LangId</i> parameters are invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>HRESULT_FROM_WIN32(ERROR_GEN_FAILURE)</dt>
</dl>
</td>
<td width="60%">
 The processing was unable to complete.

</td>
</tr>
</table>
 




## -remarks



The operating system may call this method at any time. The operating system may also store the returned pattern data to reuse later for the same set of keyword selectors.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc">CoTaskMemAlloc</a>



<a href="https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree">CoTaskMemFree</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/keyworddetectoroemadapter/nn-keyworddetectoroemadapter-ikeyworddetectoroemadapter">IKeywordDetectorOemAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/keyworddetectoroemadapter/ns-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0003">KEYWORDSELECTOR</a>
 

 

