---
UID: NS:gnssdriver.GNSS_CP_NI_INFO
title: GNSS_CP_NI_INFO (gnssdriver.h)
description: The GNSS_CP_NI_INFO structure contains CP NI information.
tech.root: gnss
ms.date: 06/20/2022
keywords: ["GNSS_CP_NI_INFO structure"]
ms.keywords: "*PGNSS_CP_NI_INFO, GNSS_CP_NI_INFO, GNSS_CP_NI_INFO structure [Sensor Devices], PGNSS_CP_NI_INFO, PGNSS_CP_NI_INFO structure pointer [Sensor Devices], gnss.gnss_cp_ni_info, gnssdriver/GNSS_CP_NI_INFO, gnssdriver/PGNSS_CP_NI_INFO"
req.header: gnssdriver.h
req.include-header: Gnssdriver.h
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
req.typenames: GNSS_CP_NI_INFO, *PGNSS_CP_NI_INFO
f1_keywords:
 - PGNSS_CP_NI_INFO
 - gnssdriver/PGNSS_CP_NI_INFO
 - GNSS_CP_NI_INFO
 - gnssdriver/GNSS_CP_NI_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_CP_NI_INFO
 - GNSS_CP_NI_INFO
---

## -description

The **GNSS_CP_NI_INFO** structure contains CP NI information.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field RequestorId

Requestor ID.

This will be displayed on the notification dialog to the user. The GNSS driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.

### -field NotificationText

Name of the client that requests the location of the device.

This will be displayed on the notification dialog to the user. The GNSS Driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.

