---
UID: NS:gnssdriver.GNSS_CWTESTDATA
title: GNSS_CWTESTDATA
author: windows-driver-content
description: This structure defines specific data elements associated with carrier wave test results returned from the driver.
old-location: sensors\gnss_cwtestdata.htm
old-project: sensors
ms.assetid: 7F1C8574-8891-4ACB-BB25-2666148E3D02
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_CWTESTDATA structure [Sensor Devices], sensors.gnss_cwtestdata, PGNSS_CWTESTDATA, *PGNSS_CWTESTDATA, gnssdriver/GNSS_CWTESTDATA, gnssdriver/PGNSS_CWTESTDATA, GNSS_CWTESTDATA, PGNSS_CWTESTDATA structure pointer [Sensor Devices]
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
-	GNSS_CWTESTDATA
product: Windows
targetos: Windows
req.typenames: *PGNSS_CWTESTDATA, GNSS_CWTESTDATA
---

# GNSS_CWTESTDATA structure


## -description


This structure defines specific data elements associated with  carrier wave test results returned from the driver.


## -syntax


````
typedef struct {
  ULONG    Size;
  ULONG    Version;
  NTSTATUS TestResultStatus;
  double   SignalToNoiseRatio;
  double   Frequency;
  BYTE     Unused[512];
} GNSS_CWTESTDATA, *PGNSS_CWTESTDATA;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field TestResultStatus

NTSTATUS value indicating whether this fix contains a valid data, or if the GNSS engine or driver encountered any errors in getting the measurements for the carrier wave test.
<ul>
<li>
Success - carrier wave test successfully started.

</li>
<li>
Failed - with error code: test not implemented, carrier wave test already in progress, fix session in progress, or other failure.

</li>
</ul>

### -field SignalToNoiseRatio

Signal to noise ratio in the carrier wave in dB-Hz.


### -field Frequency

Frequency of the carrier wave detected in the measurement band.

This frequency is provided as a difference to GPS frequency (1575.42 MHz) in kHz.


### -field Unused

 



#### - Unused[512]

Padding buffer.

