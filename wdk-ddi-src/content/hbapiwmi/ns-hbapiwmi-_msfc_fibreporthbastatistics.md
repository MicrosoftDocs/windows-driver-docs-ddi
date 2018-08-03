---
UID: NS:hbapiwmi._MSFC_FibrePortHBAStatistics
title: "_MSFC_FibrePortHBAStatistics"
author: windows-driver-content
description: The MSFC_FibrePortHBAStatistics structure is used by an HBA miniport driver that is a WMI provider to report statistics related to a fibre channel port.
old-location: storage\msfc_fibreporthbastatistics.htm
tech.root: storage
ms.assetid: 8b365e7a-6d52-417f-8c0b-78feac24602f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSFC_FibrePortHBAStatistics, MSFC_FibrePortHBAStatistics, MSFC_FibrePortHBAStatistics structure [Storage Devices], PMSFC_FibrePortHBAStatistics, PMSFC_FibrePortHBAStatistics structure pointer [Storage Devices], _MSFC_FibrePortHBAStatistics, hbapiwmi/MSFC_FibrePortHBAStatistics, hbapiwmi/PMSFC_FibrePortHBAStatistics, storage.msfc_fibreporthbastatistics, structs-Fibre_d68738f2-ea37-420f-8356-51aa06362829.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
api_name:
-	MSFC_FibrePortHBAStatistics
product:
- Windows
targetos: Windows
req.typenames: MSFC_FibrePortHBAStatistics, *PMSFC_FibrePortHBAStatistics
---

# _MSFC_FibrePortHBAStatistics structure


## -description


The MSFC_FibrePortHBAStatistics structure is used by an HBA miniport driver that is a WMI provider to report statistics related to a fibre channel port.


## -struct-fields




### -field UniquePortId

Contains a unique identifier for the port. 


### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


### -field Statistics

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff562512">MSFC_HBAPortStatistics</a> with statistical information about the port. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562505">MSFC_FibrePortHBAStatistics WMI Class</a>
 

 

