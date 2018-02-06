---
UID: NS:pointofservicedriverinterface._PosEventDataHeader
title: "_PosEventDataHeader"
author: windows-driver-content
description: This structure describes the scanned image data that is passed to the BarcodeScannerImagePreviewReceived event.
old-location: pos\posbarcodescannerimageprevieweventdata.htm
old-project: pos
ms.assetid: dc542e81-9078-4e14-8c8d-9cfaeb5b5495
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PosEventDataHeader structure, _PosEventDataHeader, pointofservicedriverinterface/PosEventDataHeader, PosBarcodeScannerImagePreviewEventData structure, pointofservicedriverinterface/PosBarcodeScannerImagePreviewEventData, PosBarcodeScannerImagePreviewEventData, pos.posbarcodescannerimageprevieweventdata, PosEventDataHeader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	PointOfServiceDriverInterface.h
apiname:
-	PosEventDataHeader
product: Windows
targetos: Windows
req.typenames: PosEventDataHeader, PosBarcodeScannerImagePreviewEventData
---

# _PosEventDataHeader structure


## -description


This structure describes the scanned image data that is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757466">BarcodeScannerImagePreviewReceived</a> event.


## -syntax


````
typedef struct _PosEventDataHeader {
  PosEventType EventType;
  UINT32       DataLength;
} PosEventDataHeader, PosBarcodeScannerImagePreviewEventData;
````


## -struct-fields




### -field EventType

The type of event. For the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757466">BarcodeScannerImagePreviewReceived</a> event the value of this field is <b>BarcodeScannerImagePreviewReceived</b>.


### -field DataLength

The length, in bytes, of the image preview data.


## -remarks


The image preview bitmap data immediately follows after this structure in memory for <i>DataLength</i> bytes.


