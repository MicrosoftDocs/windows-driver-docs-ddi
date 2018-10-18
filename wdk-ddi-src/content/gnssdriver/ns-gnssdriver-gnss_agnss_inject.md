---
UID: NS:gnssdriver.GNSS_AGNSS_INJECT
title: GNSS_AGNSS_INJECT
author: windows-driver-content
description: This structure defines the parameters for AGNSS injection.
old-location: gnss\gnss_agnss_inject.htm
tech.root: gnss
ms.assetid: B81F5D71-9928-412C-8199-787E71CE2638
ms.date: 2/15/2018
ms.keywords: "*PGNSS_AGNSS_INJECT, GNSS_AGNSS_INJECT, GNSS_AGNSS_INJECT structure [Sensor Devices], PGNSS_AGNSS_INJECT, PGNSS_AGNSS_INJECT structure pointer [Sensor Devices], gnss.gnss_agnss_inject, gnssdriver/GNSS_AGNSS_INJECT, gnssdriver/PGNSS_AGNSS_INJECT"
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
-	GNSS_AGNSS_INJECT
product:
- Windows
targetos: Windows
req.typenames: GNSS_AGNSS_INJECT, *PGNSS_AGNSS_INJECT
---

# GNSS_AGNSS_INJECT structure


## -description


This structure defines the parameters for AGNSS injection.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field InjectionType

Indicates the specific type of AGNSS injection. 

Depending on the type, the driver must access the specific data element of the structure. For example, if the type is GNSS_AGNSS_PositionInjection, use the Position element.


### -field InjectionStatus

Indicates whether any error was encountered in gathering the needed injection data. 

The driver must ignore the injection if this field does not indicate success.


### -field InjectionDataSize

Size of the injection data.


### -field Unused

 


### -field Time


<a href="https://msdn.microsoft.com/library/windows/hardware/dn925095">GNSS_AGNSS_INJECTTIME</a> contains the format for AGNSS time injection.


### -field Position


<a href="https://msdn.microsoft.com/library/windows/hardware/dn925094">GNSS_AGNSS_INJECTPOSITION</a> contains  the format for AGNSS position injection.


### -field BlobData


<a href="https://msdn.microsoft.com/library/windows/hardware/dn925093">GNSS_AGNSS_INJECTBLOB</a>  contains the format for AGNSS extended ephemeris injection.


#### - Unused[512]

Padding buffer.

