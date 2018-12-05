---
UID: NS:gnssdriver.__unnamed_struct_45
title: GNSS_SELFTESTRESULT
author: windows-driver-content
description: This structure defines the specific data elements associated with a carrier wave test results returned from the driver.
old-location: gnss\gnss_selftestresult.htm
tech.root: gnss
ms.assetid: 572A2C38-A990-4225-A3FC-6E899A248B1C
ms.date: 02/15/2018
ms.keywords: "*PGNSS_SELFTESTRESULT, GNSS_SELFTESTRESULT, GNSS_SELFTESTRESULT structure [Sensor Devices], PGNSS_SELFTESTRESULT, PGNSS_SELFTESTRESULT structure pointer [Sensor Devices], gnss.gnss_selftestresult, gnssdriver/GNSS_SELFTESTRESULT, gnssdriver/PGNSS_SELFTESTRESULT"
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
-	GNSS_SELFTESTRESULT
product:
- Windows
targetos: Windows
req.typenames: GNSS_SELFTESTRESULT, *PGNSS_SELFTESTRESULT
---

# GNSS_SELFTESTRESULT structure


## -description


This structure defines the specific data elements associated with a carrier wave test results returned from the driver.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field TestResultStatus

NTSTATUS value indicating:

<ul>
<li>
Success (self-test passed).

</li>
<li>
Failed (indicating the problem detected or indicating that the is test not implemented).

</li>
</ul>

### -field Result

The final result of the self-test.


### -field PinFailedBitMask

The bit mask for adapter pins that failed the test.


### -field Unused

 


### -field OutBufLen

The length of the buffer for returning any additional information about the self-test.


### -field OutBuffer

 




#### - OutBuffer[BYTE]

The buffer that will contain the additional information about the self-test.


#### - Unused[512]

Padding buffer.

