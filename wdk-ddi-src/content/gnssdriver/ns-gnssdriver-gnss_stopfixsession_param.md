---
UID: NS:gnssdriver.GNSS_STOPFIXSESSION_PARAM
title: GNSS_STOPFIXSESSION_PARAM
author: windows-driver-content
description: This structure is used to stop an active fix session.
old-location: sensors\gnss_stopfixsession_param.htm
old-project: sensors
ms.assetid: 37D56DC0-C35B-4651-93E9-28AF76041D5D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_STOPFIXSESSION_PARAM, *PGNSS_STOPFIXSESSION_PARAM, GNSS_STOPFIXSESSION_PARAM
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
req.alt-api: GNSS_STOPFIXSESSION_PARAM
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
req.irql: 
req.typenames: *PGNSS_STOPFIXSESSION_PARAM, GNSS_STOPFIXSESSION_PARAM
---

# GNSS_STOPFIXSESSION_PARAM structure



## -description
This structure is used to stop an active fix session.



## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG FixSessionID;
  BYTE  Unused[512];
} GNSS_STOPFIXSESSION_PARAM, *PGNSS_STOPFIXSESSION_PARAM;
````


## -struct-fields

### -field Size

Structure size.


### -field Version

Version number.


### -field FixSessionID

ID of an active fix session.


### -field Unused[512]

Padding buffer.


## -remarks
