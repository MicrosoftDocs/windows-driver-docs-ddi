---
UID: NF:sensorsdef.SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT
title: SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT function
author: windows-driver-content
description: This function calculates the number of PROPERTYKEY elements.
old-location: sensors\sensor_property_list_calculate_max_count.htm
old-project: sensors
ms.assetid: 5E639331-5929-4575-855F-CAFB4E77B66D
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT, SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT function [Sensor Devices], sensors.sensor_property_list_calculate_max_count, sensorsdef/SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sensorsdef.h
req.include-header: 
req.target-type: Desktop
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
-	Sensorsdef.h
api_name:
-	SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT
product:
- Windows
targetos: Windows
req.typenames: SENSOR_STATE
req.product: Windows 10 or later.
---

# SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT function


## -description


This function calculates the number of PROPERTYKEY elements.


## -parameters




### -param pPropertyList [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn946699">SENSOR_PROPERTY_LIST</a> structure.


## -returns



The <b>SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT</b> function returns a ULONG value that represents the number of PROPERTYKEY elements.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn946699">SENSOR_PROPERTY_LIST</a>
 

 

