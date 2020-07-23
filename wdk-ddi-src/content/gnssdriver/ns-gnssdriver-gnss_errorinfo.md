---
UID: NS:gnssdriver.__unnamed_struct_27
title: GNSS_ERRORINFO (gnssdriver.h)
description: This structure contains error information.
old-location: gnss\gnss_errorinfo.htm
tech.root: gnss
ms.assetid: 754CD1DD-88E6-4E02-8E24-1939222FE326
ms.date: 02/15/2018
keywords: ["GNSS_ERRORINFO structure"]
ms.keywords: "*PGNSS_ERRORINFO, GNSS_ERRORINFO, GNSS_ERRORINFO structure [Sensor Devices], PGNSS_ERRORINFO, PGNSS_ERRORINFO structure pointer [Sensor Devices], gnss.gnss_errorinfo, gnssdriver/GNSS_ERRORINFO, gnssdriver/PGNSS_ERRORINFO"
f1_keywords:
 - "gnssdriver/GNSS_ERRORINFO"
 - "GNSS_ERRORINFO"
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
- GNSS_ERRORINFO
targetos: Windows
req.typenames: GNSS_ERRORINFO, *PGNSS_ERRORINFO
---

# GNSS_ERRORINFO structure


## -description


This structure contains error information.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field ErrorCode

Win32 Error Code associated with the event.

The IHV can pick the error that is most similar to what needs to be reported (for example, E_OUTOFMEMORY). The IHV can also use FACILITY_ITF to create custom errors. For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=525284">Codes in FACILITY_ITF</a>.



### -field IsRecoverable

If FALSE, the GNSS adapter needs to reset it’s state with the GNSS driver.


### -field ErrorDescription

 


### -field Unused

 




#### - ErrorDescription[256]

Clear-text description of the error (not-localized) that is used for diagnostic purpose only.


#### - Unused[512]

Padding buffer.

