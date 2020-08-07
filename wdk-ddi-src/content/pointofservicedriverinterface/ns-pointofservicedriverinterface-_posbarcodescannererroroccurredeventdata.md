---
UID: NS:pointofservicedriverinterface._PosBarcodeScannerErrorOccurredEventData
title: _PosBarcodeScannerErrorOccurredEventData (pointofservicedriverinterface.h)
description: This structure contains the error data that is passed to the BarcodeScannerErrorOccurred event.
old-location: pos\posbarcodescannererroroccurredeventdata.htm
tech.root: pos
ms.assetid: c9e18ed0-bc34-49ed-a31e-20c82d43860f
ms.date: 02/23/2018
keywords: ["PosBarcodeScannerErrorOccurredEventData structure"]
ms.keywords: PosBarcodeScannerErrorOccurredEventData, PosBarcodeScannerErrorOccurredEventData structure, _PosBarcodeScannerErrorOccurredEventData, pointofservicedriverinterface/PosBarcodeScannerErrorOccurredEventData, pos.posbarcodescannererroroccurredeventdata
f1_keywords:
 - "pointofservicedriverinterface/PosBarcodeScannerErrorOccurredEventData"
 - "PosBarcodeScannerErrorOccurredEventData"
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
- PosBarcodeScannerErrorOccurredEventData
targetos: Windows
req.typenames: PosBarcodeScannerErrorOccurredEventData
---

# _PosBarcodeScannerErrorOccurredEventData structure


## -description


This structure contains the error data that is passed to the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn757464(v=vs.85)">BarcodeScannerErrorOccurred</a> event.


## -struct-fields




### -field Header

The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn772232(v=vs.85)">PosEventDataHeader</a> structure that describes the amount of memory, in bytes, of the <b>PosBarcodeScannerErrorOccurredEventData</b> structure and trailing error message and scan data.


### -field IsRetriable

Indicates whether <a href="https://go.microsoft.com/fwlink/p/?LinkId=314125">ReadFile</a> can be called again to read this event


### -field Severity

Contains a value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedposerrorseverity">UnifiedPosErrorSeverity</a> enumeration indicating the severity of the error. 


### -field VendorErrorCode

Contains a vendor-specific error code.


### -field Reason

Contains a value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedposerrorreason">UnifiedPosErrorReason</a> enumeration indicating the reason for the error.


### -field ExtendedReason

Contains additional data about the reason for the error.


### -field MessageLength

Indicates the length, in bytes, of the error message.


### -field PartialData

If a scanning error occurs, and some scan data was obtained, the partial scan data will be available in this parameter.


## -remarks



The error data should fill the buffer as shown in the following table (in order).

<table>
<tr>
<th>Data</th>
<th>Length in bytes</th>
</tr>
<tr>
<td>
<b>PosBarcodeScannerErrorOccurredEventData</b> structure

</td>
<td>
sizeof(<b>PosBarcodeScannerErrorOccurredEventData</b>)

</td>
</tr>
<tr>
<td>
Error message text

</td>
<td>
<b>MessageLength</b>

</td>
</tr>
<tr>
<td>
Partial scan data

</td>
<td>
<b>PartialData.ScanDataLength</b>

</td>
</tr>
<tr>
<td>
Label data

</td>
<td>
<b>PartialData.ScanDataLabelLength</b>

</td>
</tr>
</table>
 



