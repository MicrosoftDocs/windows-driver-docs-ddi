---
UID: NF:keyworddetectoroemadapter.IKeywordDetectorOemAdapter.VerifyUserKeyword
title: IKeywordDetectorOemAdapter::VerifyUserKeyword method
author: windows-driver-content
description: The VerifyUserKeyword method is used by the training user experience to verify that one instance of a spoken utterance, captured during training, matches a predefined keyword within some tolerance.
old-location: audio\ikeyworddetectoroemadapter_verifyuserkeyword.htm
old-project: audio
ms.assetid: AFF679B6-B389-4EA2-8834-9B1B47412B7D
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, A, D, I, IKeywordDetectorOemAdapter, IKeywordDetectorOemAdapter interface [Audio Devices], VerifyUserKeyword method, IKeywordDetectorOemAdapter::VerifyUserKeyword, K, O, U, V, VerifyUserKeyword method [Audio Devices], VerifyUserKeyword method [Audio Devices], IKeywordDetectorOemAdapter interface, VerifyUserKeyword,IKeywordDetectorOemAdapter.VerifyUserKeyword, a, audio.ikeyworddetectoroemadapter_verifyuserkeyword, c, d, e, f, i, keyworddetectoroemadapter/IKeywordDetectorOemAdapter::VerifyUserKeyword, m, o, p, r, s, t, w, y"
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
-	IKeywordDetectorOemAdapter.VerifyUserKeyword
product: Windows
targetos: Windows
req.typenames: KEYWORDID
---

# IKeywordDetectorOemAdapter::VerifyUserKeyword method


## -description


The <b>VerifyUserKeyword</b> method is used by the training user experience  to verify that one instance of a spoken utterance, captured during training, matches a predefined keyword within some tolerance.


## -syntax


````
HRESULT VerifyUserKeyword(
  [in] IStream        *ModelData,
  [in] KEYWORDID      KeywordId,
  [in] LANGID         LangId,
  [in] LONG           KeywordEndBytePos,
  [in] IMFMediaBuffer *UserRecording = 0
);
````


## -parameters




### -param ModelData [in]

A pointer to an <b>IStream</b> object bound to model data for a given stored model. On the initial call this will be empty.


### -param KeywordId [in]

The <a href="..\keyworddetectoroemadapter\ne-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0002.md">KEYWORDID</a> in the  <i>UserRecording</i> parameter.


### -param LangId [in]

The <b>LANGID</b> of the spoken language in the <i>UserRecording</i> parameter. 


### -param KeywordEndBytePos [in]

Indicates the end of the keyword in the UserRecording.


### -param UserRecording [in]

A pointer to the buffer containing the raw data in the appropriate <a href="https://msdn.microsoft.com/f1d60bec-71e4-4fcc-a020-92754b6f3c02">IMFMediaType</a> format.

The user recording must have the following attributes:

<ul>
<li>Type = Audio</li>
<li>Subtype = IEEE_FLOAT</li>
<li>Sampling Rate = 16 kHz</li>
<li>Bits = 32</li>
</ul>

## -returns



This method can return one of these values.

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
 The function exited successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
User keyword training is not supported for the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
One or more of the following conditions are true:

<ul>
<li>The <i>ModelData</i> pointer is <b>NULL</b>.</li>
<li>The <i>KeywordId</i> parameter is invalid.</li>
<li>The <i>LangId</i> parameter is invalid.</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NO_MATCH</b></dt>
</dl>
</td>
<td width="60%">
The user recording didn't contain the specified keyword.

</td>
</tr>
</table>
 




## -remarks



Note that audio is processed in a unique way for voice activation training. The following table summarizes the differences between voice activation training and the regular voice recognition usage. 

<table>
<tr>
<td></td>
<td><b>Training </b></td>
<td><b>Recognition </b></td>
</tr>
<tr>
<td>Mode</td>
<td>Raw</td>
<td>Speech</td>
</tr>
<tr>
<td>Pin</td>
<td>Normal</td>
<td>Burst</td>
</tr>
<tr>
<td> Audio Format</td>
<td>32-bit float (Type = Audio, Subtype = IEEE_FLOAT, Sampling Rate = 16 kHz, bits = 32)</td>
<td>Managed by OS audio stack</td>
</tr>
<tr>
<td>Mic</td>
<td>Mic 0 </td>
<td>All mics in array</td>
</tr>
</table>
 






## -see-also

<a href="..\keyworddetectoroemadapter\nn-keyworddetectoroemadapter-ikeyworddetectoroemadapter.md">IKeywordDetectorOemAdapter</a>



<a href="..\keyworddetectoroemadapter\ne-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0002.md">KEYWORDID</a>



<a href="https://msdn.microsoft.com/f1d60bec-71e4-4fcc-a020-92754b6f3c02">IMFMediaType</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IKeywordDetectorOemAdapter::VerifyUserKeyword method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

