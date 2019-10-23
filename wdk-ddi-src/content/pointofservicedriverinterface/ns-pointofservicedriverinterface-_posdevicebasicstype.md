---
UID: NS:pointofservicedriverinterface._PosDeviceBasicsType
title: _PosDeviceBasicsType (pointofservicedriverinterface.h)
description: This structure indicates the type of device, version, and recommended buffer size as specified by the driver.
old-location: pos\posdevicebasicstype.htm
tech.root: pos
ms.assetid: 5f882f37-0554-48c0-b4a0-026d42452f56
ms.date: 02/23/2018
ms.keywords: PosDeviceBasicsType, PosDeviceBasicsType structure, _PosDeviceBasicsType, pointofservicedriverinterface/PosDeviceBasicsType, pos.posdevicebasicstype
ms.topic: struct
f1_keywords:
 - "pointofservicedriverinterface/PosDeviceBasicsType"
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
- PosDeviceBasicsType
product:
- Windows
targetos: Windows
req.typenames: PosDeviceBasicsType
---

# _PosDeviceBasicsType structure


## -description


This structure indicates the type of device, version, and recommended buffer size as specified by the driver.


## -struct-fields




### -field Version

Contains the major and minor version of the POS driver interface. The top 16 bits contains the major version and the bottom 16 bits contains the minor version.


### -field DeviceType

Indicates the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-_posdevicetype">PosDeviceType</a> of the POS device (for example, a barcode scanner or a magnetic stripe reader).


### -field RecommendedBufferSize

Indicates the size of the buffer that needs to be allocated to receive event data when calling <a href="https://go.microsoft.com/fwlink/p/?LinkId=314125">ReadFile</a> to retrieve events for this device

