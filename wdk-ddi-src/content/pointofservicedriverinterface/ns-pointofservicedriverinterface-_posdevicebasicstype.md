---
UID: NS:pointofservicedriverinterface._PosDeviceBasicsType
title: _PosDeviceBasicsType (pointofservicedriverinterface.h)
description: This structure indicates the type of device, version, and recommended buffer size as specified by the driver.
old-location: pos\posdevicebasicstype.htm
tech.root: pos
ms.date: 08/21/2020
keywords: ["PosDeviceBasicsType structure"]
ms.keywords: PosDeviceBasicsType, PosDeviceBasicsType structure, _PosDeviceBasicsType, pointofservicedriverinterface/PosDeviceBasicsType, pos.posdevicebasicstype
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
req.typenames: PosDeviceBasicsType
f1_keywords:
 - _PosDeviceBasicsType
 - pointofservicedriverinterface/_PosDeviceBasicsType
 - PosDeviceBasicsType
 - pointofservicedriverinterface/PosDeviceBasicsType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - _PosDeviceBasicsType
 - PosDeviceBasicsType
---

# _PosDeviceBasicsType structure


## -description

This structure indicates the type of device, version, and recommended buffer size as specified by the driver.

## -struct-fields

### -field Version

Contains the major and minor version of the POS driver interface. The top 16 bits contains the major version and the bottom 16 bits contains the minor version.

### -field DeviceType

Indicates the [PosDeviceType](../pointofservicecommontypes/ne-pointofservicecommontypes-_posdevicetype.md) of the POS device (for example, a barcode scanner or a magnetic stripe reader).

### -field RecommendedBufferSize

Indicates the size of the buffer that needs to be allocated to receive event data when calling [ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile) to retrieve events for this device.

