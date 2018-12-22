---
UID: NS:gnssdriver.__unnamed_struct_31
title: GNSS_V2UPL_NI_INFO
description: This structure contains V2UPL NI information.
old-location: gnss\gnss_v2upl_ni_info.htm
tech.root: gnss
ms.assetid: 884C8141-2A15-4BAE-8A5C-73355BD84D53
ms.date: 02/15/2018
ms.keywords: "*PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO structure [Sensor Devices], PGNSS_V2UPL_NI_INFO, PGNSS_V2UPL_NI_INFO structure pointer [Sensor Devices], gnss.gnss_v2upl_ni_info, gnssdriver/GNSS_V2UPL_NI_INFO, gnssdriver/PGNSS_V2UPL_NI_INFO"
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
-	GNSS_V2UPL_NI_INFO
product:
- Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---

# GNSS_V2UPL_NI_INFO structure


## -description


This structure contains V2UPL NI information.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field RequestorId

 




#### - RequestorId[MAX_PATH]

Requestor ID.

This will be displayed on the notification dialog to the user. The GNSS driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.

