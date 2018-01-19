---
UID: NF:keyworddetectoroemadapter.IKeywordDetectorOemAdapter.ComputeAndAddUserModelData
title: IKeywordDetectorOemAdapter::ComputeAndAddUserModelData method
author: windows-driver-content
description: The ComputeAndAddUserModelData method is used by the training user experience to compute the user-specific information relative to the user-independent keyword.
old-location: audio\ikeyworddetectoroemadapter_computeandaddusermodeldata.htm
old-project: audio
ms.assetid: 4E810EAD-3864-44C1-9845-60DAB288BB48
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IKeywordDetectorOemAdapter, IKeywordDetectorOemAdapter::ComputeAndAddUserModelData, ComputeAndAddUserModelData
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
req.alt-api: IKeywordDetectorOemAdapter.ComputeAndAddUserModelData
req.alt-loc: KeywordDetectorOemAdapter.h
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
<dl>
<dt>S_OK</dt>
</dl>The function exited successfully.
<dl>
<dt>E_NOTIMPL</dt>
</dl>User keyword training is not supported by the device.
<dl>
<dt>E_INVALIDARG</dt>
</dl>Either the <i>KeywordId</i> or <i>LangId</i> parameters are invalid.
<dl>
<dt>HRESULT_FROM_WIN32(ERROR_GEN_FAILURE)</dt>
</dl>The processing was unable to complete.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\keyworddetectoroemadapter\nn-keyworddetectoroemadapter-ikeyworddetectoroemadapter.md">IKeywordDetectorOemAdapter</a>
</dt>
<dt>
<a href="..\keyworddetectoroemadapter\ns-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0003.md">KEYWORDSELECTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IKeywordDetectorOemAdapter::ComputeAndAddUserModelData method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

