---
UID: NF:keyworddetectoroemadapter.IKeywordDetectorOemAdapter.ComputeAndAddUserModelData
title: IKeywordDetectorOemAdapter::ComputeAndAddUserModelData method
author: windows-driver-content
description: The ComputeAndAddUserModelData method is used by the training user experience to compute the user-specific information relative to the user-independent keyword.
old-location: audio\ikeyworddetectoroemadapter_computeandaddusermodeldata.htm
old-project: audio
ms.assetid: 4E810EAD-3864-44C1-9845-60DAB288BB48
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: keyworddetectoroemadapter/IKeywordDetectorOemAdapter::ComputeAndAddUserModelData, ComputeAndAddUserModelData method [Audio Devices], IKeywordDetectorOemAdapter interface [Audio Devices], ComputeAndAddUserModelData method, ComputeAndAddUserModelData, IKeywordDetectorOemAdapter, audio.ikeyworddetectoroemadapter_computeandaddusermodeldata, IKeywordDetectorOemAdapter::ComputeAndAddUserModelData, ComputeAndAddUserModelData method [Audio Devices], IKeywordDetectorOemAdapter interface
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
-	IKeywordDetectorOemAdapter.ComputeAndAddUserModelData
product: Windows
targetos: Windows
req.typenames: KEYWORDID
---

# IKeywordDetectorOemAdapter::ComputeAndAddUserModelData method


## -description


The <b>ComputeAndAddUserModelData</b> method is used by the training user experience to compute the user-specific information relative to the user-independent keyword. The DLL updates the <i>ModelData</i> parameter with the results. 


## -syntax


````
HRESULT ComputeAndAddUserModelData(
  [in] IStream         *ModelData,
  [in] KEYWORDSELECTOR KeywordSelector,
  [in] LONG            KeywordEndBytePos,
  [in] IMFMediaBuffer  **UserRecordings,
  [in] ULONG           NumUserRecordings = 0
);
````


## -parameters




### -param ModelData [in]

A pointer to the <b>IStream</b> object bound to model data. It is modified by this call.


### -param KeywordSelector [in]

A <a href="..\keyworddetectoroemadapter\ns-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0003.md">KEYWORDSELECTOR</a> struct that uniquely identifies this model.


### -param KeywordEndBytePos [in]

Indicates the end of the keyword in the UserRecording.


### -param UserRecordings [in]

A pointer to an array of pointers to the previously verified user recordings of the keyword.


### -param NumUserRecordings [in]

The number of recordings.


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
<dt>E_NOTIMPL</dt>
</dl>
</td>
<td width="60%">
User keyword training is not supported by the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>E_INVALIDARG</dt>
</dl>
</td>
<td width="60%">
Either the <i>KeywordId</i> or <i>LangId</i> parameters are invalid.

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
 




## -see-also

<a href="..\keyworddetectoroemadapter\ns-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0003.md">KEYWORDSELECTOR</a>



<a href="..\keyworddetectoroemadapter\nn-keyworddetectoroemadapter-ikeyworddetectoroemadapter.md">IKeywordDetectorOemAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IKeywordDetectorOemAdapter::ComputeAndAddUserModelData method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

