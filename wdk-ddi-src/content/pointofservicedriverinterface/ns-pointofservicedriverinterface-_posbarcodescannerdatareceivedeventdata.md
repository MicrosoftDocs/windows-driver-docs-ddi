---
UID: NS:pointofservicedriverinterface._PosBarcodeScannerDataReceivedEventData
title: _PosBarcodeScannerDataReceivedEventData (pointofservicedriverinterface.h)
description: This structure contains the scanned data that is passed to the BarcodeScannerDataReceived event.
old-location: pos\posbarcodescannerdatareceivedeventdata.htm
tech.root: pos
ms.assetid: 220713c4-ecfe-43a2-aebf-f1b00b75e49b
ms.date: 02/23/2018
keywords: ["PosBarcodeScannerDataReceivedEventData structure"]
ms.keywords: PosBarcodeScannerDataReceivedEventData, PosBarcodeScannerDataReceivedEventData structure, _PosBarcodeScannerDataReceivedEventData, pointofservicedriverinterface/PosBarcodeScannerDataReceivedEventData, pos.posbarcodescannerdatareceivedeventdata
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
targetos: Windows
req.typenames: PosBarcodeScannerDataReceivedEventData
f1_keywords:
 - _PosBarcodeScannerDataReceivedEventData
 - pointofservicedriverinterface/_PosBarcodeScannerDataReceivedEventData
 - PosBarcodeScannerDataReceivedEventData
 - pointofservicedriverinterface/PosBarcodeScannerDataReceivedEventData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - PosBarcodeScannerDataReceivedEventData
---

# _PosBarcodeScannerDataReceivedEventData structure


## -description

This structure contains the scanned data that is passed to the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn757463(v=vs.85)">BarcodeScannerDataReceived</a> event.

## -struct-fields

### -field Header

The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn772232(v=vs.85)">PosEventDataHeader</a> header information for this event.

### -field DataType

Indicates which <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-_barcodesymbology">BarcodeSymbology</a> is associated with the scan data.

### -field ScanDataLength

Indicates the number of bytes of raw scanned data.

### -field ScanDataLabelLength

Indicates the number of bytes of decoded scan data. A label is the decoded scan data in which the header and footer information has been removed, leaving only the raw scanner data.

## -remarks

*ScanDataLength* bytes of scan data immediately follows the *PosBarcodeScannerDataReceivedEventData* structure, followed by *ScanDataLabelLength* bytes of label data.

