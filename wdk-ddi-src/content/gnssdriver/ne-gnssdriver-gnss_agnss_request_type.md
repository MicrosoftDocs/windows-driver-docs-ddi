---
UID: NE:gnssdriver.GNSS_AGNSS_REQUEST_TYPE
title: GNSS_AGNSS_REQUEST_TYPE
author: windows-driver-content
description: This enumeration indicates the type of AGNSS injection request represented by the GNSS_AGNSS_REQUEST_PARAM structure.
old-location: sensors\gnss_agnss_request_type.htm
old-project: sensors
ms.assetid: 31293354-D68B-475F-91BD-0504129207A5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_AGNSS_PositionInjection, gnssdriver/GNSS_AGNSS_TimeInjection, GNSS_AGNSS_TimeInjection, gnssdriver/GNSS_AGNSS_PositionInjection, GNSS_AGNSS_REQUEST_TYPE, gnssdriver/GNSS_AGNSS_REQUEST_TYPE, sensors.gnss_agnss_request_type, gnssdriver/GNSS_AGNSS_BlobInjection, GNSS_AGNSS_BlobInjection, GNSS_AGNSS_REQUEST_TYPE enumeration [Sensor Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: gnssdriver.h
req.include-header: 
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	GNSS_AGNSS_REQUEST_TYPE
product: Windows
targetos: Windows
req.typenames: GNSS_AGNSS_REQUEST_TYPE
---

# GNSS_AGNSS_REQUEST_TYPE enumeration


## -description


This enumeration indicates the type of AGNSS injection request represented by the <a href="..\gnssdriver\ns-gnssdriver-gnss_agnss_request_param.md">GNSS_AGNSS_REQUEST_PARAM</a> structure.


## -syntax


````
typedef enum  { 
  GNSS_AGNSS_TimeInjection      = 0x01,
  GNSS_AGNSS_PositionInjection  = 0x02,
  GNSS_AGNSS_BlobInjection      = 0x03
} GNSS_AGNSS_REQUEST_TYPE;
````


## -enum-fields




#### - GNSS_AGNSS_TimeInjection

Indicates the injection request is for time injection.


#### - GNSS_AGNSS_PositionInjection

Indicates the injection request is for position injection.


#### - GNSS_AGNSS_BlobInjection

Indicates the injection request is for blob injection.

