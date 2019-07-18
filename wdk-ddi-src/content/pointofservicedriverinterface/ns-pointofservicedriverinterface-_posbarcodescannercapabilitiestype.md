---
UID: NS:pointofservicedriverinterface._PosBarcodeScannerCapabilitiesType
title: _PosBarcodeScannerCapabilitiesType (pointofservicedriverinterface.h)
description: This structure defines the type of scanner capabilities that a device supports such as whether the device supports statistics reporting and image preview.
old-location: pos\posbarcodescannercapabilitiestype.htm
tech.root: pos
ms.assetid: 4387e6f4-c980-4339-a89c-0e71c5a79e2c
ms.date: 02/23/2018
ms.keywords: PosBarcodeScannerCapabilitiesType, PosBarcodeScannerCapabilitiesType structure, _PosBarcodeScannerCapabilitiesType, pointofservicedriverinterface/PosBarcodeScannerCapabilitiesType, pos.posbarcodescannercapabilitiestype
ms.topic: struct
f1_keywords:
 - "pointofservicedriverinterface/PosBarcodeScannerCapabilitiesType"
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
- PosBarcodeScannerCapabilitiesType
product:
- Windows
targetos: Windows
req.typenames: PosBarcodeScannerCapabilitiesType
---

# _PosBarcodeScannerCapabilitiesType structure


## -description


This structure defines the type of scanner capabilities that a device supports such as whether the device supports statistics reporting and image preview.


## -struct-fields




### -field PowerReportingType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedpospowerreportingtype">UnifiedPosPowerReportingType</a> that indicates whether the device supports standard or advanced power reporting.


### -field IsStatisticsReportingSupported

Indicates whether <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_retrieve_statistics">IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS</a> is supported.


### -field IsStatisticsUpdatingSupported

Indicates whether <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_update_statistics">IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS</a> is supported. 


### -field IsImagePreviewSupported

Indicates whether image data can be obtained from the barcode scanner device (in other words, whether <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn757466(v=vs.85)">BarcodeScannerImagePreviewReceived</a> events will be sent by the driver).

