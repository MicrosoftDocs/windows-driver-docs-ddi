---
UID: NE:sensorsdef.PEDOMETER_STEP_TYPE_COUNT
title: PEDOMETER_STEP_TYPE_COUNT
author: windows-driver-content
description: This enumeration represents the number of step types that can be detected by the pedometer.
old-location: sensors\pedometer_step_type_count.htm
old-project: sensors
ms.assetid: BED8C7F8-AF7A-4C82-BDE2-51C4285FF510
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: sensors.pedometer_step_type_count, PedometerStepTypeCount, PEDOMETER_STEP_TYPE_COUNT, sensorsdef/PedometerStepTypeCount, sensorsdef/PEDOMETER_STEP_TYPE_COUNT, PEDOMETER_STEP_TYPE_COUNT enumeration [Sensor Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sensorsdef.h
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
-	Sensorsdef.h
apiname: 
-	PEDOMETER_STEP_TYPE_COUNT
product: Windows
targetos: Windows
req.typenames: PEDOMETER_STEP_TYPE_COUNT
req.product: Windows 10 or later.
---

# PEDOMETER_STEP_TYPE_COUNT enumeration


## -description


This enumeration represents the number of step types that can be detected by the pedometer.


## -syntax


````
typedef enum _PEDOMETER_STEP_TYPE_COUNT { 
  PedometerStepTypeCount  = 3
} PEDOMETER_STEP_TYPE_COUNT;
````


## -enum-fields




### -field PedometerStepTypeCount

The number of step types that can be detected.


## -see-also

<a href="..\sensorsdef\ne-sensorsdef-pedometer_step_type.md">PEDOMETER_STEP_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20PEDOMETER_STEP_TYPE_COUNT enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

