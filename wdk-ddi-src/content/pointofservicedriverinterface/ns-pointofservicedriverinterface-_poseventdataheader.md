---
UID: NS:pointofservicedriverinterface._PosEventDataHeader
title: _PosEventDataHeader (pointofservicedriverinterface.h)
description: This structure describes the scanned image data that is passed to the BarcodeScannerImagePreviewReceived event.
old-location: pos\posbarcodescannerimageprevieweventdata.htm
tech.root: pos
ms.assetid: dc542e81-9078-4e14-8c8d-9cfaeb5b5495
ms.date: 02/23/2018
keywords: ["_PosEventDataHeader structure"]
ms.keywords: PosBarcodeScannerImagePreviewEventData, PosBarcodeScannerImagePreviewEventData structure, PosEventDataHeader, PosEventDataHeader structure, _PosEventDataHeader, pointofservicedriverinterface/PosBarcodeScannerImagePreviewEventData, pointofservicedriverinterface/PosEventDataHeader, pos.posbarcodescannerimageprevieweventdata
f1_keywords:
 - "pointofservicedriverinterface/PosEventDataHeader"
 - "PosEventDataHeader"
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- PointOfServiceDriverInterface.h
api_name:
- PosEventDataHeader
targetos: Windows
req.typenames: PosEventDataHeader, PosBarcodeScannerImagePreviewEventData
---

# _PosEventDataHeader structure


## -description


This structure describes the scanned image data that is passed to the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn757466(v=vs.85)">BarcodeScannerImagePreviewReceived</a> event.


## -struct-fields




### -field EventType

The type of event. For the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn757466(v=vs.85)">BarcodeScannerImagePreviewReceived</a> event the value of this field is <b>BarcodeScannerImagePreviewReceived</b>.


### -field DataLength

The length, in bytes, of the image preview data.


## -remarks



The image preview bitmap data immediately follows after this structure in memory for <i>DataLength</i> bytes.



