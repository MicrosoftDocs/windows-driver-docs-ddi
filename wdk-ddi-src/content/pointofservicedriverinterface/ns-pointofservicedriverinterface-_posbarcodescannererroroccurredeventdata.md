---
UID: NS:pointofservicedriverinterface._PosBarcodeScannerErrorOccurredEventData
title: _PosBarcodeScannerErrorOccurredEventData (pointofservicedriverinterface.h)
description: This structure contains the error data that is passed to the BarcodeScannerErrorOccurred event.
old-location: pos\posbarcodescannererroroccurredeventdata.htm
tech.root: pos
ms.assetid: c9e18ed0-bc34-49ed-a31e-20c82d43860f
ms.date: 08/21/2020
keywords: ["PosBarcodeScannerErrorOccurredEventData structure"]
ms.keywords: PosBarcodeScannerErrorOccurredEventData, PosBarcodeScannerErrorOccurredEventData structure, _PosBarcodeScannerErrorOccurredEventData, pointofservicedriverinterface/PosBarcodeScannerErrorOccurredEventData, pos.posbarcodescannererroroccurredeventdata
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
req.typenames: PosBarcodeScannerErrorOccurredEventData
f1_keywords:
 - _PosBarcodeScannerErrorOccurredEventData
 - pointofservicedriverinterface/_PosBarcodeScannerErrorOccurredEventData
 - PosBarcodeScannerErrorOccurredEventData
 - pointofservicedriverinterface/PosBarcodeScannerErrorOccurredEventData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - PosBarcodeScannerErrorOccurredEventData
---

# _PosBarcodeScannerErrorOccurredEventData structure


## -description

This structure contains the error data that is passed to the [BarcodeScannerErrorOccurred](/previous-versions/windows/hardware/previsioning-framework/dn757464(v=vs.85)) event.

## -struct-fields

### -field Header

The [PosEventDataHeader](/previous-versions/windows/hardware/previsioning-framework/dn772232(v=vs.85)) structure that describes the amount of memory, in bytes, of the **PosBarcodeScannerErrorOccurredEventData** structure and trailing error message and scan data.

### -field IsRetriable

Indicates whether [ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile) can be called again to read this event

### -field Severity

Contains a value in the [UnifiedPosErrorSeverity](../pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedposerrorseverity.md) enumeration indicating the severity of the error.

### -field VendorErrorCode

Contains a vendor-specific error code.

### -field Reason

Contains a value in the [UnifiedPosErrorReason](../pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedposerrorreason.md) enumeration indicating the reason for the error.

### -field ExtendedReason

Contains additional data about the reason for the error.

### -field MessageLength

Indicates the length, in bytes, of the error message.

### -field PartialData

If a scanning error occurs, and some scan data was obtained, the partial scan data will be available in this parameter.

## -remarks

The error data should fill the buffer as shown in the following table (in order).

| Data | Length in bytes |
|--|--|
| **PosBarcodeScannerErrorOccurredEventData** structure | sizeof(**PosBarcodeScannerErrorOccurredEventData**) |
| Error message text | **MessageLength** |
| Partial scan data | **PartialData.ScanDataLength** |
| Label data | **PartialData.ScanDataLabelLength** |