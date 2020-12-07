---
UID: NS:hbapiwmi._MSFC_FibrePortHBAAttributes
title: _MSFC_FibrePortHBAAttributes (hbapiwmi.h)
description: A WMI provider uses the MSFC_FibrePortHBAAttributes WMI class to expose attribute information associated with a fibre channel port.
old-location: storage\msfc_fibreporthbaattributes.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MSFC_FibrePortHBAAttributes structure"]
ms.keywords: "*PMSFC_FibrePortHBAAttributes, MSFC_FibrePortHBAAttributes, MSFC_FibrePortHBAAttributes structure [Storage Devices], PMSFC_FibrePortHBAAttributes, PMSFC_FibrePortHBAAttributes structure pointer [Storage Devices], _MSFC_FibrePortHBAAttributes, hbapiwmi/MSFC_FibrePortHBAAttributes, hbapiwmi/PMSFC_FibrePortHBAAttributes, storage.msfc_fibreporthbaattributes, structs-Fibre_8721cac7-a44b-4401-991d-1b8822aec5be.xml"
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
targetos: Windows
req.typenames: MSFC_FibrePortHBAAttributes, *PMSFC_FibrePortHBAAttributes
f1_keywords:
 - _MSFC_FibrePortHBAAttributes
 - hbapiwmi/_MSFC_FibrePortHBAAttributes
 - PMSFC_FibrePortHBAAttributes
 - hbapiwmi/PMSFC_FibrePortHBAAttributes
 - MSFC_FibrePortHBAAttributes
 - hbapiwmi/MSFC_FibrePortHBAAttributes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - MSFC_FibrePortHBAAttributes
---

# _MSFC_FibrePortHBAAttributes structure


## -description

A WMI provider uses the MSFC_FibrePortHBAAttributes WMI class to expose attribute information associated with a fibre channel port.

## -struct-fields

### -field UniquePortId

Unique identifier for the port. This identifier must be unique among all ports on all adapters. The same value for the identifier must be used for the same port in other classes that expose port information.

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

### -field Attributes

Contains a structure of type <a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_msfc_hbaportattributesresults">MSFC_HBAPortAttributesResults</a> that contains information about the port attributes.

## -see-also

<a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>



<a href="/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_msfc_hbaportattributesresults">MSFC_HBAPortAttributesResults</a>
