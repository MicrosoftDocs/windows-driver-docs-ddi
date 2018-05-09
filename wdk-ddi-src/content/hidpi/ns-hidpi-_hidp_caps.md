---
UID: NS:hidpi._HIDP_CAPS
title: "_HIDP_CAPS"
author: windows-driver-content
description: The HIDP_CAPS structure contains information about a top-level collection's capability.
old-location: hid\hidp_caps.htm
old-project: hid
ms.assetid: ec4d4b7b-acf6-4839-9a61-1883eddce3f4
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PHIDP_CAPS, HIDP_CAPS, HIDP_CAPS structure [Human Input Devices], PHIDP_CAPS, PHIDP_CAPS structure pointer [Human Input Devices], _HIDP_CAPS, hid.hidp_caps, hidpi/HIDP_CAPS, hidpi/PHIDP_CAPS, hidstrct_2ef93e42-2fd2-4dff-87fb-11f1d1342b07.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	hidpi.h
api_name:
-	HIDP_CAPS
product:
- Windows
targetos: Windows
req.typenames: HIDP_CAPS, *PHIDP_CAPS
---

# _HIDP_CAPS structure


## -description


The HIDP_CAPS structure contains information about a top-level <a href="https://msdn.microsoft.com/228fab4f-ff90-43c5-bc68-26b29e8a7dd6">collection's capability</a>.


## -struct-fields




### -field UsagePage

Specifies the top-level collection's <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a>.


### -field Usage

Specifies a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage ID</a>.


### -field InputReportByteLength

Specifies the maximum size, in bytes, of all the input reports (including the report ID, if report IDs are used, which is prepended to the report data).


### -field OutputReportByteLength

Specifies the maximum size, in bytes, of all the output reports (including the report ID, if report IDs are used, which is prepended to the report data).


### -field FeatureReportByteLength

Specifies the maximum length, in bytes, of all the feature reports (including the report ID, if report IDs are used, which is prepended to the report data).


### -field Reserved

Reserved for internal system use.


### -field NumberLinkCollectionNodes

Specifies the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539764">HIDP_LINK_COLLECTION_NODE</a> structures that are returned for this top-level collection by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539725">HidP_GetLinkCollectionNodes</a>.


### -field NumberInputButtonCaps

Specifies the number of input <a href="https://msdn.microsoft.com/library/windows/hardware/ff539693">HIDP_BUTTON_CAPS</a> structures that <a href="https://msdn.microsoft.com/library/windows/hardware/ff539707">HidP_GetButtonCaps</a> returns.


### -field NumberInputValueCaps

Specifies the number of input <a href="https://msdn.microsoft.com/library/windows/hardware/ff539832">HIDP_VALUE_CAPS</a> structures that <a href="https://msdn.microsoft.com/library/windows/hardware/ff539754">HidP_GetValueCaps</a> returns.


### -field NumberInputDataIndices

Specifies the number of <a href="https://msdn.microsoft.com/84577544-515a-4fdc-86e5-518182c6c461">data indices</a> assigned to buttons and values in all input reports.


### -field NumberOutputButtonCaps

Specifies the number of output HIDP_BUTTON_CAPS structures that <b>HidP_GetButtonCaps</b> returns.


### -field NumberOutputValueCaps

Specifies the number of output HIDP_VALUE_CAPS structures that <b>HidP_GetValueCaps</b> returns.


### -field NumberOutputDataIndices

Specifies the number of data indices assigned to buttons and values in all output reports.


### -field NumberFeatureButtonCaps

Specifies the total number of feature HIDP_BUTTONS_CAPS structures that <b>HidP_GetButtonCaps</b> returns.


### -field NumberFeatureValueCaps

Specifies the total number of feature HIDP_VALUE_CAPS structures that <b>HidP_GetValueCaps</b> returns.


### -field NumberFeatureDataIndices

Specifies the number of data indices assigned to buttons and values in all feature reports.


## -remarks



Callers of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538865">HIDClass support routines</a> use the information provided in this structure when a called routine requires, as input, the size of a report type, the number of link collection nodes, the number of control capabilities, or the number of data indices.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539693">HIDP_BUTTON_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539764">HIDP_LINK_COLLECTION_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539832">HIDP_VALUE_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539707">HidP_GetButtonCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539715">HidP_GetCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539725">HidP_GetLinkCollectionNodes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539733">HidP_GetSpecificButtonCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539737">HidP_GetSpecificValueCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539754">HidP_GetValueCaps</a>
 

 

