---
UID: NS:gnssdriver.GNSS_SELFTESTCONFIG
title: GNSS_SELFTESTCONFIG
author: windows-driver-content
description: This structure defines the specific data elements associated with a carrier wave test results returned from the driver.
old-location: sensors\gnss_selftestconfig.htm
old-project: sensors
ms.assetid: DE0D4A9A-F85D-4AA4-8A21-1BEC86837444
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PGNSS_SELFTESTCONFIG structure pointer [Sensor Devices], GNSS_SELFTESTCONFIG, sensors.gnss_selftestconfig, PGNSS_SELFTESTCONFIG, *PGNSS_SELFTESTCONFIG, gnssdriver/PGNSS_SELFTESTCONFIG, GNSS_SELFTESTCONFIG structure [Sensor Devices], gnssdriver/GNSS_SELFTESTCONFIG
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
-	GNSS_SELFTESTCONFIG
product: Windows
targetos: Windows
req.typenames: GNSS_SELFTESTCONFIG, *PGNSS_SELFTESTCONFIG
---

# GNSS_SELFTESTCONFIG structure


## -description


This structure defines the specific data elements associated with a carrier wave test results returned from the driver.


## -syntax


````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG TestType;
  BYTE  Unused[512];
  ULONG InBufLen;
  BYTE  InBuffer[ANYSIZE_ARRAY];
} GNSS_SELFTESTCONFIG, *PGNSS_SELFTESTCONFIG;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field TestType

The type of self-test requested.


### -field Unused

 


### -field InBufLen

The length of the buffer for passing in any additional information about the self-test.


### -field InBuffer

 




#### - Unused[512]

Padding buffer.


#### - InBuffer[ANYSIZE_ARRAY]

The buffer that will contain the additional information about the self-test.

