---
UID: NS:pointofservicedriverinterface._PosBarcodeScannerCapabilitiesType
title: _PosBarcodeScannerCapabilitiesType (pointofservicedriverinterface.h)
description: This structure defines the type of scanner capabilities that a device supports such as whether the device supports statistics reporting and image preview.
old-location: pos\posbarcodescannercapabilitiestype.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["PosBarcodeScannerCapabilitiesType structure"]
ms.keywords: PosBarcodeScannerCapabilitiesType, PosBarcodeScannerCapabilitiesType structure, _PosBarcodeScannerCapabilitiesType, pointofservicedriverinterface/PosBarcodeScannerCapabilitiesType, pos.posbarcodescannercapabilitiestype
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
req.typenames: PosBarcodeScannerCapabilitiesType
f1_keywords:
 - _PosBarcodeScannerCapabilitiesType
 - pointofservicedriverinterface/_PosBarcodeScannerCapabilitiesType
 - PosBarcodeScannerCapabilitiesType
 - pointofservicedriverinterface/PosBarcodeScannerCapabilitiesType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - _PosBarcodeScannerCapabilitiesType
 - PosBarcodeScannerCapabilitiesType
---

# _PosBarcodeScannerCapabilitiesType structure


## -description

This structure defines the type of scanner capabilities that a device supports such as whether the device supports statistics reporting and image preview.

## -struct-fields

### -field PowerReportingType

A <a href="/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedpospowerreportingtype">UnifiedPosPowerReportingType</a> that indicates whether the device supports standard or advanced power reporting.

### -field IsStatisticsReportingSupported

Indicates whether <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_retrieve_statistics">IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS</a> is supported.

### -field IsStatisticsUpdatingSupported

Indicates whether <a href="/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_update_statistics">IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS</a> is supported.

### -field IsImagePreviewSupported

Indicates whether image data can be obtained from the barcode scanner device (in other words, whether <a href="/previous-versions/windows/hardware/previsioning-framework/dn757466(v=vs.85)">BarcodeScannerImagePreviewReceived</a> events will be sent by the driver).

