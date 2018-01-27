---
UID: NE:sensorsdef.MAGNETOMETER_ACCURACY
title: MAGNETOMETER_ACCURACY
author: windows-driver-content
description: This enumeration represents the accuracy states of the magnetometer.
old-location: sensors\magnetometer_accuracy.htm
old-project: sensors
ms.assetid: BC8D4FB1-69F4-4FAE-BA90-7CCB57D4A6C4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: MagnetometerAccuracy_Unreliable, sensorsdef/MagnetometerAccuracy_High, sensors.magnetometer_accuracy, MagnetometerAccuracy_High, sensorsdef/MagnetometerAccuracy_Unreliable, sensorsdef/MagnetometerAccuracy_Unknown, MagnetometerAccuracy_Approximate, MagnetometerAccuracy_Unknown, MAGNETOMETER_ACCURACY enumeration [Sensor Devices], sensorsdef/MagnetometerAccuracy_Approximate, MAGNETOMETER_ACCURACY, sensorsdef/MAGNETOMETER_ACCURACY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sensorsdef.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	Sensorsdef.h
apiname: 
-	MAGNETOMETER_ACCURACY
product: Windows
targetos: Windows
req.typenames: MAGNETOMETER_ACCURACY
req.product: Windows 10 or later.
---

# MAGNETOMETER_ACCURACY enumeration


## -description


This enumeration represents the accuracy states of the magnetometer.


## -syntax


````
typedef enum _MAGNETOMETER_ACCURACY { 
  MagnetometerAccuracy_Unknown      = 0,
  MagnetometerAccuracy_Unreliable,
  MagnetometerAccuracy_Approximate,
  MagnetometerAccuracy_High
} MAGNETOMETER_ACCURACY;
````


## -enum-fields




### -field MagnetometerAccuracy_Unknown

Indicates that the magnetometer's accuracy cannot be determined.


### -field MagnetometerAccuracy_Unreliable

Indicates that the magnetometer readings are unreliable. The application can choose to prompt the user to calibrate the compass, to improve accuracy.


### -field MagnetometerAccuracy_Approximate

Indicates that the magnetometer readings are approximate values.


### -field MagnetometerAccuracy_High

Indicates that the magnetometer accuracy is set to high.

