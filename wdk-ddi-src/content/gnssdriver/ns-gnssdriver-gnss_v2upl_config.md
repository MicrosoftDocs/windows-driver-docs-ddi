---
UID: NS:gnssdriver.GNSS_V2UPL_CONFIG
title: GNSS_V2UPL_CONFIG
author: windows-driver-content
description: This structure contains V2UPL configuration information.
old-location: sensors\gnss_v2upl_config.htm
old-project: sensors
ms.assetid: A1DCC547-8CAA-46B9-A855-5F591C69A3B0
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PGNSS_V2UPL_CONFIG, GNSS_V2UPL_CONFIG, GNSS_V2UPL_CONFIG structure [Sensor Devices], PGNSS_V2UPL_CONFIG, PGNSS_V2UPL_CONFIG structure pointer [Sensor Devices], gnssdriver/GNSS_V2UPL_CONFIG, gnssdriver/PGNSS_V2UPL_CONFIG, sensors.gnss_v2upl_config"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_V2UPL_CONFIG
product:
- Windows
targetos: Windows
req.typenames: GNSS_V2UPL_CONFIG, *PGNSS_V2UPL_CONFIG
---

# GNSS_V2UPL_CONFIG structure


## -description


This structure contains V2UPL configuration information.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field MPC

 


### -field PDE

 


### -field ApplicationTypeIndicator_MR

Application type indicator for any mobile originated location request to the MPC. It shall be set to the value for Microsoft resident applications based on intelligent platform.


### -field Unused

 




#### - MPC[MAX_SERVER_URL_NAME]

MPC address and port number.


#### - PDE[MAX_SERVER_URL_NAME]

PDE address and port number.

