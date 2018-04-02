---
UID: NS:hbapiwmi._MSFC_FibrePortHBAAttributes
title: "_MSFC_FibrePortHBAAttributes"
author: windows-driver-content
description: A WMI provider uses the MSFC_FibrePortHBAAttributes WMI class to expose attribute information associated with a fibre channel port.
old-location: storage\msfc_fibreporthbaattributes.htm
old-project: storage
ms.assetid: e8a31f48-bad2-49d1-81be-d345d87a0fd5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSFC_FibrePortHBAAttributes, MSFC_FibrePortHBAAttributes, MSFC_FibrePortHBAAttributes structure [Storage Devices], PMSFC_FibrePortHBAAttributes, PMSFC_FibrePortHBAAttributes structure pointer [Storage Devices], _MSFC_FibrePortHBAAttributes, hbapiwmi/MSFC_FibrePortHBAAttributes, hbapiwmi/PMSFC_FibrePortHBAAttributes, storage.msfc_fibreporthbaattributes, structs-Fibre_8721cac7-a44b-4401-991d-1b8822aec5be.xml"
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
-	MSFC_FibrePortHBAAttributes
product:
- Windows
targetos: Windows
req.typenames: MSFC_FibrePortHBAAttributes, *PMSFC_FibrePortHBAAttributes
---

# _MSFC_FibrePortHBAAttributes structure


## -description


A WMI provider uses the MSFC_FibrePortHBAAttributes WMI class to expose attribute information associated with a fibre channel port.


## -struct-fields




### -field UniquePortId

Unique identifier for the port. This identifier must be unique among all ports on all adapters. The same value for the identifier must be used for the same port in other classes that expose port information.


### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


### -field Attributes

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff562510">MSFC_HBAPortAttributesResults</a> that contains information about the port attributes. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562510">MSFC_HBAPortAttributesResults</a>
 

 

