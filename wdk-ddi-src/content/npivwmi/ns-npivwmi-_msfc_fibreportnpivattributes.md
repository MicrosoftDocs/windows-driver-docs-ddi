---
UID: NS:npivwmi._MSFC_FibrePortNPIVAttributes
title: _MSFC_FibrePortNPIVAttributes (npivwmi.h)
description: The MSFC_FibrePortNPIVAttributes structure contains attribute information for the virtual ports on an adapter.
old-location: storage\msfc_fibreportnpivattributes.htm
tech.root: storage
ms.assetid: 1641C3A0-E6D9-4E30-9E3C-3C09A14F591F
ms.date: 03/29/2018
ms.keywords: "*PMSFC_FibrePortNPIVAttributes, MSFC_FibrePortNPIVAttributes, MSFC_FibrePortNPIVAttributes structure [Storage Devices], PMSFC_FibrePortNPIVAttributes, PMSFC_FibrePortNPIVAttributes structure pointer [Storage Devices], _MSFC_FibrePortNPIVAttributes, npivwmi/MSFC_FibrePortNPIVAttributes, npivwmi/PMSFC_FibrePortNPIVAttributes, storage.msfc_fibreportnpivattributes"
ms.topic: struct
f1_keywords:
 - "npivwmi/MSFC_FibrePortNPIVAttributes"
req.header: npivwmi.h
req.include-header: Npivwmi.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- npivwmi.h
api_name:
- MSFC_FibrePortNPIVAttributes
product:
- Windows
targetos: Windows
req.typenames: MSFC_FibrePortNPIVAttributes, *PMSFC_FibrePortNPIVAttributes
---

# _MSFC_FibrePortNPIVAttributes structure


## -description


The MSFC_FibrePortNPIVAttributes structure contains attribute information for the virtual ports on an adapter.


## -struct-fields




### -field WWPN

The world wide port name of the physical port.


### -field WWNN

The world wide node name of the physical port.


### -field NumberVirtualPorts

The number of virtual ports on the adapter.


### -field VirtualPorts

An array of virtual ports. The array length is specified in the <b>NumberVirtualPorts</b> member.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-fibreportnpivattributes-wmi-class">MSFC_FibrePortNPIVAttributes WMI Class</a>
 

 

