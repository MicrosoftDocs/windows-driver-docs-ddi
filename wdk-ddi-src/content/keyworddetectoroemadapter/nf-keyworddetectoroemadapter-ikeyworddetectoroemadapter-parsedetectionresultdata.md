---
UID: NF:keyworddetectoroemadapter.IKeywordDetectorOemAdapter.ParseDetectionResultData
title: IKeywordDetectorOemAdapter::ParseDetectionResultData method
author: windows-driver-content
description: The ParseDetectionResultData method is called by the operating system after handling a keyword detection event and after retrieving the result data from KSPROPERTY_SOUNDDETECTOR_MATCHRESULT.
old-location: audio\ikeyworddetectoroemadapter_parsedetectionresultdata.htm
old-project: audio
ms.assetid: 97C92A85-BE00-4B95-80D1-20FE7A31BCA9
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IKeywordDetectorOemAdapter, IKeywordDetectorOemAdapter interface [Audio Devices], ParseDetectionResultData method, IKeywordDetectorOemAdapter::ParseDetectionResultData, ParseDetectionResultData method [Audio Devices], ParseDetectionResultData method [Audio Devices], IKeywordDetectorOemAdapter interface, ParseDetectionResultData,IKeywordDetectorOemAdapter.ParseDetectionResultData, audio.ikeyworddetectoroemadapter_parsedetectionresultdata, keyworddetectoroemadapter/IKeywordDetectorOemAdapter::ParseDetectionResultData
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
-	IKeywordDetectorOemAdapter.ParseDetectionResultData
product: Windows
targetos: Windows
req.typenames: KEYWORDID
---

# IKeywordDetectorOemAdapter::ParseDetectionResultData method


## -description


The <b>ParseDetectionResultData</b> method is called by the operating system after handling a keyword detection event and after retrieving the result data from <a href="https://msdn.microsoft.com/library/windows/hardware/dn932150">KSPROPERTY_SOUNDDETECTOR_MATCHRESULT</a>. The operating system passes the OEM-specific match result data to this method in order to get the results of a keyword detection.  The OEMDLL processes the results and returns information about the matched keyword, the language associated with the matched keyword, and the matched user (if any).


## -parameters




### -param UserModelData [in]

A pointer to <b>IStream</b> bound to model data for the arming pattern.




### -param Result [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn957513">SOUNDDETECTOR_PATTERNHEADER</a> from the DDI.



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


If the driver returns <i>KeywordStartTime</i> or <i>KeywordEndTime</i>, the returned values must be consistent with the time stamps returned from the driver’s <a href="https://msdn.microsoft.com/library/windows/hardware/dn946533">IMiniportWaveRTInputStream::GetReadPacket</a> routine.


The driver may return valid values for <i>KeywordStartTime</i> and <i>KeywordEndTime</i> regardless of whether the driver includes any portion of the spoken keyword in the burst keyword/command stream.


If the caller receives <b>E_HW_RESET</b>, no keyword was detected by the hardware and the state was lost. A re-arm will be required to get back to a monitoring state.




## -see-also




<a href="https://msdn.microsoft.com/c4cb588d-9482-4f90-a92e-75b604540d5c">CoTaskMemAlloc</a>



<a href="https://msdn.microsoft.com/3d0af12e-fc74-4ef7-b2dd-e9da5d0483c7">CoTaskMemFree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn957504">IKeywordDetectorOemAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn946533">IMiniportWaveRTInputStream::GetReadPacket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn932150">KSPROPERTY_SOUNDDETECTOR_MATCHRESULT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn957513">SOUNDDETECTOR_PATTERNHEADER</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IKeywordDetectorOemAdapter::ParseDetectionResultData method%20 RELEASE:%20(3/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

