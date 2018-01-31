---
UID: NF:sensorsdef.SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
title: SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function
author: windows-driver-content
description: This function calculates the number of SENSOR_VALUE_PAIR elements in a SENSOR_COLLECTION_LIST structure.
old-location: sensors\sensor_collection_list_calculate_max_count.htm
old-project: sensors
ms.assetid: 56C94717-41FF-44AA-BC99-1ECE4A407A38
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: sensors.sensor_collection_list_calculate_max_count, SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function [Sensor Devices], sensorsdef/SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT, SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
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
req.lib: NtosKrnl.exe
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
-	SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT
product: Windows
targetos: Windows
req.typenames: SENSOR_STATE
req.product: Windows 10 or later.
---

# SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function


## -description


This function calculates the number of <a href="..\sensorsdef\ns-sensorsdef-sensor_value_pair.md">SENSOR_VALUE_PAIR</a> elements in a <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a> structure.


## -syntax


````
FORCEINLINE ULONG SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT(
  _In_ PSENSOR_COLLECTION_LIST pCollectionList
);
````


## -parameters




#### - pCollectionList [in]

A pointer to a <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a> structure.


## -returns


The <b>SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT</b> function returns a ULONG value.



## -see-also

<a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>

<a href="..\sensorsdef\ns-sensorsdef-sensor_value_pair.md">SENSOR_VALUE_PAIR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

