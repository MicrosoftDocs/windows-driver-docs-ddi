---
UID: NF:keyworddetectoroemadapter.IKeywordDetectorOemAdapter.ParseDetectionResultData
title: IKeywordDetectorOemAdapter::ParseDetectionResultData (keyworddetectoroemadapter.h)
description: The ParseDetectionResultData method is called by the operating system after handling a keyword detection event and after retrieving the result data from KSPROPERTY_SOUNDDETECTOR_MATCHRESULT.
old-location: audio\ikeyworddetectoroemadapter_parsedetectionresultdata.htm
tech.root: audio
ms.assetid: 97C92A85-BE00-4B95-80D1-20FE7A31BCA9
ms.date: 05/08/2018
ms.keywords: IKeywordDetectorOemAdapter interface [Audio Devices],ParseDetectionResultData method, IKeywordDetectorOemAdapter.ParseDetectionResultData, IKeywordDetectorOemAdapter::ParseDetectionResultData, ParseDetectionResultData, ParseDetectionResultData method [Audio Devices], ParseDetectionResultData method [Audio Devices],IKeywordDetectorOemAdapter interface, audio.ikeyworddetectoroemadapter_parsedetectionresultdata, keyworddetectoroemadapter/IKeywordDetectorOemAdapter::ParseDetectionResultData
f1_keywords:
 - "keyworddetectoroemadapter/IKeywordDetectorOemAdapter.ParseDetectionResultData"
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
- IKeywordDetectorOemAdapter.ParseDetectionResultData
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKeywordDetectorOemAdapter::ParseDetectionResultData


## -description


The <b>ParseDetectionResultData</b> method is called by the operating system after handling a keyword detection event and after retrieving the result data from <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-sounddetector-matchresult">KSPROPERTY_SOUNDDETECTOR_MATCHRESULT</a>. The operating system passes the OEM-specific match result data to this method in order to get the results of a keyword detection.  The OEMDLL processes the results and returns information about the matched keyword, the language associated with the matched keyword, and the matched user (if any).


## -parameters




### -param UserModelData [in]

A pointer to <b>IStream</b> bound to model data for the arming pattern.




### -param Result [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-sounddetector_patternheader">SOUNDDETECTOR_PATTERNHEADER</a> from the DDI.



### -param KeywordId [out]

Identifies a keyword function. The driver may return 0 to indicate no match.


### -param LangId [out]

Identifies a language.


### -param pIsUserMatch [out]

Indicates if the user matched.


### -param KeywordStartPerformanceCounterValue




### -param KeywordEndPerformanceCounterValue






#### - KeywordEndPerformanceCounter [out]

Optionally returns the end time of the keyword in terms of the Windows performance counter. The OEMDLL should return 0 if this is not available.


#### - KeywordStartPerformanceCounter [out]

Optionally returns the start time of the keyword in terms of the Windows performance counter. The OEMDLL should return 0 if this is not available.


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
<tr>
<td width="40%">
<dl>
<dt>E_HW_RESET</dt>
</dl>
</td>
<td width="60%">
The hardware reset due to an internal fault.

</td>
</tr>
</table>
 




## -remarks



If the driver includes any portion of the spoken keyword in the burst keyword/command stream from its keyword detector pin, then the driver must return a valid value for <i>KeywordEndTime</i>. Otherwise the driver may optionally return 0.


If the driver returns <i>KeywordStartTime</i> or <i>KeywordEndTime</i>, the returned values must be consistent with the time stamps returned from the driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavertinputstream-getreadpacket">IMiniportWaveRTInputStream::GetReadPacket</a> routine.


The driver may return valid values for <i>KeywordStartTime</i> and <i>KeywordEndTime</i> regardless of whether the driver includes any portion of the spoken keyword in the burst keyword/command stream.


If the caller receives <b>E_HW_RESET</b>, no keyword was detected by the hardware and the state was lost. A re-arm will be required to get back to a monitoring state.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc">CoTaskMemAlloc</a>



<a href="https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree">CoTaskMemFree</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/keyworddetectoroemadapter/nn-keyworddetectoroemadapter-ikeyworddetectoroemadapter">IKeywordDetectorOemAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavertinputstream-getreadpacket">IMiniportWaveRTInputStream::GetReadPacket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-sounddetector-matchresult">KSPROPERTY_SOUNDDETECTOR_MATCHRESULT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-sounddetector_patternheader">SOUNDDETECTOR_PATTERNHEADER</a>
 

 

