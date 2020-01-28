---
UID: NS:gnssdriver.__unnamed_struct_33
title: GNSS_DRIVER_REQUEST_DATA (gnssdriver.h)
description: This structure contains driver data request information.
old-location: gnss\gnss_driver_request_data.htm
tech.root: gnss
ms.assetid: 801FBD9D-304A-41AC-AD28-00DE95DEFE63
ms.date: 02/15/2018
ms.keywords: GNSS_DRIVER_REQUEST_DATA, GNSS_DRIVER_REQUEST_DATA structure [Sensor Devices], PGNSS_DRIVER_REQUEST_DATA, PGNSS_DRIVER_REQUEST_DATA structure pointer [Sensor Devices], gnss.gnss_driver_request_data, gnssdriver/GNSS_DRIVER_REQUEST_DATA, gnssdriver/PGNSS_DRIVER_REQUEST_DATA
f1_keywords:
 - "gnssdriver/GNSS_DRIVER_REQUEST_DATA"
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
- GNSS_DRIVER_REQUEST_DATA
product:
- Windows
targetos: Windows
req.typenames: GNSS_DRIVER_REQUEST_DATA
---

# GNSS_DRIVER_REQUEST_DATA structure


## -description


This structure contains driver data request information.




## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field Request

The type of request made by the driver.

Represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ne-gnssdriver-gnss_driver_request">GNSS_DRIVER_REQUEST</a> enumeration.


### -field RequestFlag

Additional flags along with this information.


## -remarks



Based on certain rules, the HLOS  will provide data to the GNSS driver. However, during specific  times, if the GNSS driver determines that it needs  data it can request it without waiting for the HLOS to send it in its normal operation.



