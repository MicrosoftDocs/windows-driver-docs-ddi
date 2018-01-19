---
UID: NS:gnssdriver.GNSS_AGNSS_INJECTTIME
title: GNSS_AGNSS_INJECTTIME
author: windows-driver-content
description: This structure defines the format for AGNSS time injection.
old-location: sensors\gnss_agnss_injecttime.htm
old-project: sensors
ms.assetid: 05BCC40C-E542-4BE8-9FD7-F0D25C3B8C7C
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_AGNSS_INJECTTIME, GNSS_AGNSS_INJECTTIME, *PGNSS_AGNSS_INJECTTIME
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
req.alt-api: GNSS_AGNSS_INJECTTIME
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
req.typenames: GNSS_AGNSS_INJECTTIME, *PGNSS_AGNSS_INJECTTIME
---

# GNSS_AGNSS_INJECTTIME structure



## -description
This structure defines the format for AGNSS time injection.



## -syntax

````
typedef struct {
  ULONG    Size;
  ULONG    Version;
  FILETIME UtcTime;
  ULONG    TimeUncertainty;
} GNSS_AGNSS_INJECTTIME, *PGNSS_AGNSS_INJECTTIME;
````


## -struct-fields

### -field Size

Structure size.


### -field Version

Version number.


### -field UtcTime

UTC time.


### -field TimeUncertainty

Uncertainty in milliseconds.


## -remarks
