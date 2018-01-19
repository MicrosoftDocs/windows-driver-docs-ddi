---
UID: NE:gnssdriver.GNSS_DRIVER_REQUEST
title: GNSS_DRIVER_REQUEST
author: windows-driver-content
description: GNSS_DRIVER_REQUEST enumerates the GNSS driver data request types.
old-location: sensors\gnss_driver_request.htm
old-project: sensors
ms.assetid: 923774E0-4F4E-470A-9793-8AD4261AEB64
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_DRIVER_REQUEST, GNSS_DRIVER_REQUEST
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
req.alt-api: GNSS_DRIVER_REQUEST
req.alt-loc: gnssdriver.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: GNSS_DRIVER_REQUEST
---

# GNSS_DRIVER_REQUEST enumeration



## -description
GNSS_DRIVER_REQUEST enumerates  the GNSS driver data request types. 



## -syntax

````
typedef enum  { 
  SUPL_CONFIG_DATA  = 0x01
} GNSS_DRIVER_REQUEST;
````


## -enum-fields

### -field SUPL_CONFIG_DATA

This is used by the GNSS driver to  request SUPL configuration data.


## -remarks
