---
UID: NS:pointofservicedriverinterface._PosBarcodeScannerDataReceivedEventData
title: "_PosBarcodeScannerDataReceivedEventData"
author: windows-driver-content
description: This structure contains the scanned data that is passed to the BarcodeScannerDataReceived event.
old-location: pos\posbarcodescannerdatareceivedeventdata.htm
tech.root: pos
ms.assetid: 220713c4-ecfe-43a2-aebf-f1b00b75e49b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosBarcodeScannerDataReceivedEventData, PosBarcodeScannerDataReceivedEventData structure, _PosBarcodeScannerDataReceivedEventData, pointofservicedriverinterface/PosBarcodeScannerDataReceivedEventData, pos.posbarcodescannerdatareceivedeventdata
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	PointOfServiceDriverInterface.h
api_name:
-	PosBarcodeScannerDataReceivedEventData
product:
- Windows
targetos: Windows
req.typenames: PosBarcodeScannerDataReceivedEventData
---

# _PosBarcodeScannerDataReceivedEventData structure


## -description


This structure contains the scanned data that is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn757463">BarcodeScannerDataReceived</a> event.


## -struct-fields




### -field Header

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn772232">PosEventDataHeader</a> header information for this event.


### -field DataType

Indicates which <a href="https://msdn.microsoft.com/library/windows/hardware/dn757474">BarcodeSymbology</a> is associated with the scan data.


### -field ScanDataLength

Indicates the number of bytes of raw scanned data.


### -field ScanDataLabelLength

Indicates the number of bytes of decoded scan data. A label is the decoded scan data in which the header and footer information has been removed, leaving only the raw scanner data. 


## -remarks



<i>ScanDataLength</i> bytes of scan data immediately follows the <i>PosBarcodeScannerDataReceivedEventData</i> structure, followed by <i>ScanDataLabelLength</i> bytes of label data.



