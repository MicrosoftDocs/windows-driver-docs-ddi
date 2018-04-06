---
UID: NS:hbaapi.HBA_FC4Statistics
title: HBA_FC4Statistics
author: windows-driver-content
description: The HBA_FC4Statistics structure contains port statistics.
old-location: storage\hba_fc4statistics.htm
old-project: storage
ms.assetid: e1e37d2c-5688-4528-9cc5-62e70a7561fe
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PHBA_FC4STATISTICS, HBA_FC4STATISTICS, HBA_FC4STATISTICS structure [Storage Devices], HBA_FC4Statistics, HBA_FC4Statistics structure [Storage Devices], PHBA_FC4STATISTICS, PHBA_FC4STATISTICS structure pointer [Storage Devices], hbaapi/HBA_FC4Statistics, hbaapi/PHBA_FC4STATISTICS, storage.hba_fc4statistics, structs-Fibre_1ab7a8f5-1b91-44ea-82b7-9c9ee92ce0e5.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
-	hbaapi.h
api_name:
-	HBA_FC4STATISTICS
product:
- Windows
targetos: Windows
req.typenames: HBA_FC4STATISTICS, *PHBA_FC4STATISTICS
---

# HBA_FC4Statistics structure


## -description


The <b>HBA_FC4Statistics</b> structure contains port statistics. 


## -struct-fields




### -field InputRequests

Contains the number of input requests that a port has received.


### -field OutputRequests

Contains the number of output requests that a port has received.


### -field ControlRequests

Contains the number of control requests that a port has received.


### -field InputMegabytes

Contains the number of megabytes of input data that a port has received.


### -field OutputMegabytes

Contains the number of megabytes of output data that a port has transmitted.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556093">HBA_GetFC4Statistics</a>
 

 

