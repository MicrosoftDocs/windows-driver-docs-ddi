---
UID: NS:gnssdriver.GNSS_SELFTESTCONFIG
title: GNSS_SELFTESTCONFIG
author: windows-driver-content
description: This structure defines the specific data elements associated with a carrier wave test results returned from the driver.
old-location: gnss\gnss_selftestconfig.htm
tech.root: gnss
ms.assetid: DE0D4A9A-F85D-4AA4-8A21-1BEC86837444
ms.date: 2/15/2018
ms.keywords: "*PGNSS_SELFTESTCONFIG, GNSS_SELFTESTCONFIG, GNSS_SELFTESTCONFIG structure [Sensor Devices], PGNSS_SELFTESTCONFIG, PGNSS_SELFTESTCONFIG structure pointer [Sensor Devices], gnss.gnss_selftestconfig, gnssdriver/GNSS_SELFTESTCONFIG, gnssdriver/PGNSS_SELFTESTCONFIG"
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
-	GNSS_SELFTESTCONFIG
product:
- Windows
targetos: Windows
req.typenames: GNSS_SELFTESTCONFIG, *PGNSS_SELFTESTCONFIG
---

# GNSS_SELFTESTCONFIG structure


## -description


This structure defines the specific data elements associated with a carrier wave test results returned from the driver.


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

 




#### - InBuffer[ANYSIZE_ARRAY]

The buffer that will contain the additional information about the self-test.


#### - Unused[512]

Padding buffer.

