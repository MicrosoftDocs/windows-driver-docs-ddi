---
UID: NS:npivwmi._MSFC_NPIVLUNMappingInformation
title: _MSFC_NPIVLUNMappingInformation (npivwmi.h)
description: The MSFC_NPIVLUNMappingInformation structure contains the Logical Unit Number (LUN) to virtual port mapping information.
old-location: storage\msfc_npivlunmappinginformation.htm
tech.root: storage
ms.assetid: 5E8A2338-AF1E-41BE-870B-E1F1877DDEDD
ms.date: 03/29/2018
keywords: ["MSFC_NPIVLUNMappingInformation structure"]
ms.keywords: "*PMSFC_NPIVLUNMappingInformation, MSFC_NPIVLUNMappingInformation, MSFC_NPIVLUNMappingInformation structure [Storage Devices], PMSFC_NPIVLUNMappingInformation, PMSFC_NPIVLUNMappingInformation structure pointer [Storage Devices], _MSFC_NPIVLUNMappingInformation, npivwmi/MSFC_NPIVLUNMappingInformation, npivwmi/PMSFC_NPIVLUNMappingInformation, storage.msfc_npivlunmappinginformation"
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
targetos: Windows
req.typenames: MSFC_NPIVLUNMappingInformation, *PMSFC_NPIVLUNMappingInformation
f1_keywords:
 - _MSFC_NPIVLUNMappingInformation
 - npivwmi/_MSFC_NPIVLUNMappingInformation
 - PMSFC_NPIVLUNMappingInformation
 - npivwmi/PMSFC_NPIVLUNMappingInformation
 - MSFC_NPIVLUNMappingInformation
 - npivwmi/MSFC_NPIVLUNMappingInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - npivwmi.h
api_name:
 - MSFC_NPIVLUNMappingInformation
---

# _MSFC_NPIVLUNMappingInformation structure


## -description

The MSFC_NPIVLUNMappingInformation structure contains the Logical Unit Number (LUN) to virtual port mapping information.

## -struct-fields

### -field WWPNVirtualPort

The world wide port name of the virtual port.

### -field WWPNPhysicalPort

The world wide port name of the physical port.

### -field OSBus

The path ID of the LUN  mapped to the virtual port.

### -field OSTarget

The target device ID number of the LUN mapped to the virtual port.

### -field OSLUN

The LUN mapped to the virtual port.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-npivlunmappinginformation-wmi-class">MSFC_NPIVLUNMappingInformation WMI Class</a>

