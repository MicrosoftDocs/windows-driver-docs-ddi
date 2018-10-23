---
UID: NS:gnssdriver.GNSS_CHIPSETINFO
title: GNSS_CHIPSETINFO
author: windows-driver-content
description: This structure defines the specific data elements associated with the GNSS hardware.
old-location: gnss\gnss_chipsetinfo.htm
tech.root: gnss
ms.assetid: DE45805C-09E6-44B8-A4DA-BF73EC444AA9
ms.date: 02/15/2018
ms.keywords: "*PGNSS_CHIPSETINFO, GNSS_CHIPSETINFO, GNSS_CHIPSETINFO structure [Sensor Devices], PGNSS_CHIPSETINFO, PGNSS_CHIPSETINFO structure pointer [Sensor Devices], gnss.gnss_chipsetinfo, gnssdriver/GNSS_CHIPSETINFO, gnssdriver/PGNSS_CHIPSETINFO"
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
-	GNSS_CHIPSETINFO
product:
- Windows
targetos: Windows
req.typenames: GNSS_CHIPSETINFO, *PGNSS_CHIPSETINFO
---

# GNSS_CHIPSETINFO structure


## -description


This structure defines the specific data elements associated with the GNSS hardware.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field ManufacturerID

 


### -field HardwareID

 


### -field FirmwareVersion

 


### -field Unused

 




#### - FirmwareVersion[20]

Version for the firmware for the. This would be a string, typically of the format NNNN.NNNN.NNNN.NNNN.


#### - HardwareID[25]

String containing an identifier for the specific GNSS chipset or combo chipset.


#### - ManufacturerID[25]

String containing an identifier for the manufacturer.


#### - Unused[512]

Padding buffer.

