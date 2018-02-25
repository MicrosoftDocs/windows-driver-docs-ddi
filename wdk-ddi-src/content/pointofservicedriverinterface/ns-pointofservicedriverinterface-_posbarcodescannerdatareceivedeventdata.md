---
UID: NS:pointofservicedriverinterface._PosBarcodeScannerDataReceivedEventData
title: "_PosBarcodeScannerDataReceivedEventData"
author: windows-driver-content
description: This structure contains the scanned data that is passed to the BarcodeScannerDataReceived event.
old-location: pos\posbarcodescannerdatareceivedeventdata.htm
old-project: pos
ms.assetid: 220713c4-ecfe-43a2-aebf-f1b00b75e49b
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, B, D, E, P, PosBarcodeScannerDataReceivedEventData, PosBarcodeScannerDataReceivedEventData structure, R, S, _, _PosBarcodeScannerDataReceivedEventData, a, c, d, e, i, n, o, pointofservicedriverinterface/PosBarcodeScannerDataReceivedEventData, pos.posbarcodescannerdatareceivedeventdata, r, s, t, v"
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
-	PosBarcodeScannerDataReceivedEventData
product: Windows
targetos: Windows
req.typenames: PosBarcodeScannerDataReceivedEventData
---

# _PosBarcodeScannerDataReceivedEventData structure


## -description


This structure contains the scanned data that is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757463">BarcodeScannerDataReceived</a> event.


## -syntax


````
typedef struct _PosBarcodeScannerDataReceivedEventData {
  PosEventDataHeader Header;
  UINT32             DataType;
  UINT32             ScanDataLength;
  UINT32             ScanDataLabelLength;
} PosBarcodeScannerDataReceivedEventData;
````


## -struct-fields




### -field Header

The <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_poseventdataheader.md">PosEventDataHeader</a> header information for this event.


### -field DataType

Indicates which <a href="..\pointofservicecommontypes\ne-pointofservicecommontypes-_barcodesymbology.md">BarcodeSymbology</a> is associated with the scan data.


### -field ScanDataLength

Indicates the number of bytes of raw scanned data.


### -field ScanDataLabelLength

Indicates the number of bytes of decoded scan data. A label is the decoded scan data in which the header and footer information has been removed, leaving only the raw scanner data. 


## -remarks



<i>ScanDataLength</i> bytes of scan data immediately follows the <i>PosBarcodeScannerDataReceivedEventData</i> structure, followed by <i>ScanDataLabelLength</i> bytes of label data.



