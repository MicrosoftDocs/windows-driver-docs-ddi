---
UID: NS:pointofservicedriverinterface._PosBarcodeScanDataTypeData
title: _PosBarcodeScanDataTypeData (pointofservicedriverinterface.h)
description: This structure describes a buffer of barcode symbologies supported by the driver.
old-location: pos\posbarcodescandatatypedata.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["PosBarcodeScanDataTypeData structure"]
ms.keywords: PosBarcodeScanDataTypeData, PosBarcodeScanDataTypeData structure, _PosBarcodeScanDataTypeData, pointofservicedriverinterface/PosBarcodeScanDataTypeData, pos.posbarcodescandatatypedata
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
req.typenames: PosBarcodeScanDataTypeData
f1_keywords:
 - _PosBarcodeScanDataTypeData
 - pointofservicedriverinterface/_PosBarcodeScanDataTypeData
 - PosBarcodeScanDataTypeData
 - pointofservicedriverinterface/PosBarcodeScanDataTypeData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - _PosBarcodeScanDataTypeData
 - PosBarcodeScanDataTypeData
---

# _PosBarcodeScanDataTypeData structure


## -description

This structure describes a buffer of barcode symbologies supported by the driver.

## -struct-fields

### -field dataLengthInBytes

The size of the buffer that contains the symbologies, including the size of the **PosBarcodeScanDataTypeData** structure.

### -field scanDataTypes_0

The start of the DWORD array of symbologies.

## -remarks

Each symbology in the buffer is represented by a DWORD. The size of the array of symboligies that scanDataTypes_0 points to is <code>scanDataTypes_0/sizeof(UINT32) - 1;</code>

