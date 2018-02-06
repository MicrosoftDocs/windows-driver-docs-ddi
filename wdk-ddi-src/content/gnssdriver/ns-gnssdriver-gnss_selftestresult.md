---
UID: NS:gnssdriver.GNSS_SELFTESTRESULT
title: GNSS_SELFTESTRESULT
author: windows-driver-content
description: This structure defines the specific data elements associated with a carrier wave test results returned from the driver.
old-location: sensors\gnss_selftestresult.htm
old-project: sensors
ms.assetid: 572A2C38-A990-4225-A3FC-6E899A248B1C
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: gnssdriver/PGNSS_SELFTESTRESULT, PGNSS_SELFTESTRESULT, GNSS_SELFTESTRESULT, GNSS_SELFTESTRESULT structure [Sensor Devices], gnssdriver/GNSS_SELFTESTRESULT, *PGNSS_SELFTESTRESULT, sensors.gnss_selftestresult, PGNSS_SELFTESTRESULT structure pointer [Sensor Devices]
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
-	GNSS_SELFTESTRESULT
product: Windows
targetos: Windows
req.typenames: GNSS_SELFTESTRESULT, *PGNSS_SELFTESTRESULT
---

# GNSS_SELFTESTRESULT structure


## -description


This structure defines the specific data elements associated with a carrier wave test results returned from the driver.


## -syntax


````
typedef struct {
  ULONG    Size;
  ULONG    Version;
  NTSTATUS TestResultStatus;
  ULONG    Result;
  ULONG    PinFailedBitMask;
  BYTE     Unused[512];
  ULONG    OutBufLen;
  BYTE     OutBuffer[BYTE];
} GNSS_SELFTESTRESULT, *PGNSS_SELFTESTRESULT;
````


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

 



#### - Unused[512]

Padding buffer.


#### - OutBuffer[BYTE]

The buffer that will contain the additional information about the self-test.

