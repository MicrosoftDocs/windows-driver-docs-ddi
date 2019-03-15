---
UID: NS:gnssdriver.__unnamed_struct_4
title: GNSS_SINGLESHOT_PARAM (gnssdriver.h)
description: This structure defines the parameters for a single-shot fix session.
old-location: gnss\gnss_singleshot_param.htm
tech.root: gnss
ms.assetid: BD1CB6CE-4196-4B85-AED0-A7B8ED957ADF
ms.date: 02/15/2018
ms.keywords: "*PGNSS_SINGLESHOT_PARAM, GNSS_SINGLESHOT_PARAM, GNSS_SINGLESHOT_PARAM structure [Sensor Devices], PGNSS_SINGLESHOT_PARAM, PGNSS_SINGLESHOT_PARAM structure pointer [Sensor Devices], gnss.gnss_singleshot_param, gnssdriver/GNSS_SINGLESHOT_PARAM, gnssdriver/PGNSS_SINGLESHOT_PARAM"
ms.topic: struct
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- gnssdriver.h
api_name:
- GNSS_SINGLESHOT_PARAM
product:
- Windows
targetos: Windows
req.typenames: GNSS_SINGLESHOT_PARAM, *PGNSS_SINGLESHOT_PARAM
---

# GNSS_SINGLESHOT_PARAM structure


## -description


This structure defines the parameters for a single-shot fix session.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field ResponseTime

Response time is maximum remaining time that an application can wait for a fix or an error. 

Since the driver is expected to return intermediate fixes the ResponseTime is only an advisory information for the driver that can be used in an implementation-specific manner for making appropriate tradeoffs internally to satisfy the request. A value of 0 indicate that no specific response time is mandated by the GNSS adapter for the fix session.

