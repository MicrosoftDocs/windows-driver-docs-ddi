---
UID: NS:gnssdriver.GNSS_ERRORINFO
title: GNSS_ERRORINFO
author: windows-driver-content
description: This structure contains error information.
old-location: sensors\gnss_errorinfo.htm
old-project: sensors
ms.assetid: 754CD1DD-88E6-4E02-8E24-1939222FE326
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PGNSS_ERRORINFO, GNSS_ERRORINFO, GNSS_ERRORINFO structure [Sensor Devices], PGNSS_ERRORINFO, PGNSS_ERRORINFO structure pointer [Sensor Devices], gnssdriver/GNSS_ERRORINFO, gnssdriver/PGNSS_ERRORINFO, sensors.gnss_errorinfo"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	GNSS_ERRORINFO
product: Windows
targetos: Windows
req.typenames: GNSS_ERRORINFO, *PGNSS_ERRORINFO
---

# GNSS_ERRORINFO structure


## -description


This structure contains error information.


## -syntax


````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG ErrorCode;
  BOOL  IsRecoverable;
  WCHAR ErrorDescription[256];
  BYTE  Unused[512];
} GNSS_ERRORINFO, *PGNSS_ERRORINFO;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field ErrorCode

Win32 Error Code associated with the event.

The IHV can pick the error that is most similar to what needs to be reported (for example, E_OUTOFMEMORY). The IHV can also use FACILITY_ITF to create custom errors. For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=525284">Codes in FACILITY_ITF</a>.



### -field IsRecoverable

If FALSE, the GNSS adapter needs to reset it’s state with the GNSS driver.


### -field ErrorDescription

 


### -field Unused

 




#### - ErrorDescription[256]

Clear-text description of the error (not-localized) that is used for diagnostic purpose only.


#### - Unused[512]

Padding buffer.

