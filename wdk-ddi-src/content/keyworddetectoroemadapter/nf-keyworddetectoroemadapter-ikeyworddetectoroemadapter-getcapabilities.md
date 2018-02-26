---
UID: NF:keyworddetectoroemadapter.IKeywordDetectorOemAdapter.GetCapabilities
title: IKeywordDetectorOemAdapter::GetCapabilities method
author: windows-driver-content
description: The GetCapabilities method returns the keywords and languages supported by the object.
old-location: audio\ikeyworddetectoroemadapter_getcapabilities.htm
old-project: audio
ms.assetid: 5885E2BB-78DA-46F5-8330-DE8785C61946
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, A, C, D, G, GetCapabilities method [Audio Devices], GetCapabilities method [Audio Devices], IKeywordDetectorOemAdapter interface, GetCapabilities,IKeywordDetectorOemAdapter.GetCapabilities, I, IKeywordDetectorOemAdapter, IKeywordDetectorOemAdapter interface [Audio Devices], GetCapabilities method, IKeywordDetectorOemAdapter::GetCapabilities, K, O, a, audio.ikeyworddetectoroemadapter_getcapabilities, b, c, d, e, i, keyworddetectoroemadapter/IKeywordDetectorOemAdapter::GetCapabilities, l, m, o, p, r, s, t, w, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: keyworddetectoroemadapter.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	KeywordDetectorOemAdapter.h
apiname:
-	IKeywordDetectorOemAdapter.GetCapabilities
product: Windows
targetos: Windows
req.typenames: KEYWORDID
---

# IKeywordDetectorOemAdapter::GetCapabilities method


## -description


The <b>GetCapabilities</b> method returns the keywords and languages supported by the object.


## -syntax


````
HRESULT GetCapabilities(
  [in]  Bool         *SupportsUserModels,
  [out] KEYWORDID    **KeywordIds,
  [out] ULONG        *NumKeywords,
  [out] LANGID       **LangIds,
  [out] ULONG        *NumLanguages,
  [out] IMFMediaType **ppMediaType = 0
);
````


## -parameters




### -param SupportsUserModels [in]

A Boolean value that indicates whether user specific training is supported. 


### -param KeywordIds [out]

A pointer to an array of keyword IDs supported by the object. The object allocates the array by calling <a href="https://msdn.microsoft.com/c4cb588d-9482-4f90-a92e-75b604540d5c">CoTaskMemAlloc</a>. The caller frees the memory by calling <a href="https://msdn.microsoft.com/3d0af12e-fc74-4ef7-b2dd-e9da5d0483c7">CoTaskMemFree</a>.


### -param NumKeywords [out]

The number of keyword IDs in the <i>KeywordIds</i> array.


### -param LangIds [out]

A pointer to an array of language IDs supported by the object. The object allocates the array by calling <a href="https://msdn.microsoft.com/c4cb588d-9482-4f90-a92e-75b604540d5c">CoTaskMemAlloc</a>. The caller frees the memory by calling <a href="https://msdn.microsoft.com/3d0af12e-fc74-4ef7-b2dd-e9da5d0483c7">CoTaskMemFree</a>.


### -param NumLanguages [out]

The number of language IDs in the <i>LangIds</i> array.


### -param ppMediaType [out]

The audio format required by <a href="https://msdn.microsoft.com/library/windows/hardware/dn957509">IKeywordDetectorOemAdapter::VerifyUserKeyword</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn957506">IKeywordDetectorOemAdapter::ComputeAndAddUserModelData</a>. 

The only valid values for the IMFMediaType are the following:

<ul>
<li>Type = Audio</li>
<li>Subtype = IEEE_FLOAT</li>
<li>Sampling Rate = 16 kHz</li>
<li>Bits = 32</li>
</ul>
Typically, the OEMDLL calls <a href="https://msdn.microsoft.com/05b0941e-03ce-4ced-9022-22b65d1c4b4c">MFCreateMediaType</a> and <a href="https://msdn.microsoft.com/91a201a6-06cf-4445-ad62-fdabb3848d51">MFInitMediaTypeFromWaveFormatEx</a> to obtain an <a href="https://msdn.microsoft.com/f1d60bec-71e4-4fcc-a020-92754b6f3c02">IMFMediaType</a> pointer to return to the caller.


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
The pointer for an output parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>E_INVALIDARG</dt>
</dl>
</td>
<td width="60%">
The pointer to the model data is <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



The information returned from this routine would normally not change for a given version of the OEMDLL or the user independent model data installed along with it.


The OEMDLL must have internal user independent models for the keywords and languages returned from this method.





## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn957506">IKeywordDetectorOemAdapter::ComputeAndAddUserModelData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn957509">IKeywordDetectorOemAdapter::VerifyUserKeyword</a>



<a href="https://msdn.microsoft.com/91a201a6-06cf-4445-ad62-fdabb3848d51">MFInitMediaTypeFromWaveFormatEx</a>



<a href="https://msdn.microsoft.com/05b0941e-03ce-4ced-9022-22b65d1c4b4c">MFCreateMediaType</a>



<a href="..\keyworddetectoroemadapter\nn-keyworddetectoroemadapter-ikeyworddetectoroemadapter.md">IKeywordDetectorOemAdapter</a>



<a href="https://msdn.microsoft.com/3d0af12e-fc74-4ef7-b2dd-e9da5d0483c7">CoTaskMemFree</a>



<a href="https://msdn.microsoft.com/f1d60bec-71e4-4fcc-a020-92754b6f3c02">IMFMediaType</a>



<a href="https://msdn.microsoft.com/c4cb588d-9482-4f90-a92e-75b604540d5c">CoTaskMemAlloc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IKeywordDetectorOemAdapter::GetCapabilities method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

