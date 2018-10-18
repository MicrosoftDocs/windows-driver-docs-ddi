---
UID: NF:keyworddetectoroemadapter.IKeywordDetectorOemAdapter.ComputeAndAddUserModelData
title: IKeywordDetectorOemAdapter::ComputeAndAddUserModelData
author: windows-driver-content
description: The ComputeAndAddUserModelData method is used by the training user experience to compute the user-specific information relative to the user-independent keyword.
old-location: audio\ikeyworddetectoroemadapter_computeandaddusermodeldata.htm
tech.root: audio
ms.assetid: 4E810EAD-3864-44C1-9845-60DAB288BB48
ms.date: 5/8/2018
ms.keywords: ComputeAndAddUserModelData, ComputeAndAddUserModelData method [Audio Devices], ComputeAndAddUserModelData method [Audio Devices],IKeywordDetectorOemAdapter interface, IKeywordDetectorOemAdapter interface [Audio Devices],ComputeAndAddUserModelData method, IKeywordDetectorOemAdapter.ComputeAndAddUserModelData, IKeywordDetectorOemAdapter::ComputeAndAddUserModelData, audio.ikeyworddetectoroemadapter_computeandaddusermodeldata, keyworddetectoroemadapter/IKeywordDetectorOemAdapter::ComputeAndAddUserModelData
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	KeywordDetectorOemAdapter.h
api_name:
-	IKeywordDetectorOemAdapter.ComputeAndAddUserModelData
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKeywordDetectorOemAdapter::ComputeAndAddUserModelData


## -description


The <b>ComputeAndAddUserModelData</b> method is used by the training user experience to compute the user-specific information relative to the user-independent keyword. The DLL updates the <i>ModelData</i> parameter with the results. 


## -parameters




### -param ModelData [in]

A pointer to the <b>IStream</b> object bound to model data. It is modified by this call.


### -param KeywordSelector [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn957511">KEYWORDSELECTOR</a> struct that uniquely identifies this model.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/dn957504">IKeywordDetectorOemAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn957511">KEYWORDSELECTOR</a>
 

 

