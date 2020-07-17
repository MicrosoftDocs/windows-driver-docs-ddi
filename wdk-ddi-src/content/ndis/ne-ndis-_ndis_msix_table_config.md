---
UID: NE:ndis._NDIS_MSIX_TABLE_CONFIG
title: _NDIS_MSIX_TABLE_CONFIG (ndis.h)
description: The NDIS_MSIX_TABLE_OPERATION enumeration identifies the type of MSI-X configuration operation.
old-location: netvista\ndis_msix_table_operation.htm
tech.root: netvista
ms.assetid: 7d1a4bb6-5db8-48b0-9be3-7468360951a1
ms.date: 05/02/2018
keywords: ["_NDIS_MSIX_TABLE_CONFIG enumeration"]
ms.keywords: "*PNDIS_MSIX_TABLE_OPERATION, NDIS_MSIX_TABLE_OPERATION, NDIS_MSIX_TABLE_OPERATION enumeration [Network Drivers Starting with Windows Vista], NdisMSIXTableConfigMaskTableEntry, NdisMSIXTableConfigMax, NdisMSIXTableConfigSetTableEntry, NdisMSIXTableConfigUnmaskTableEntry, PNDIS_MSIX_TABLE_OPERATION, PNDIS_MSIX_TABLE_OPERATION enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_MSIX_TABLE_CONFIG, ndis/NDIS_MSIX_TABLE_OPERATION, ndis/NdisMSIXTableConfigMaskTableEntry, ndis/NdisMSIXTableConfigMax, ndis/NdisMSIXTableConfigSetTableEntry, ndis/NdisMSIXTableConfigUnmaskTableEntry, ndis/PNDIS_MSIX_TABLE_OPERATION, ndis_msix_ref_b315600c-7d23-4251-bcdb-560c46d5fa79.xml, netvista.ndis_msix_table_operation"
f1_keywords:
 - "ndis/NDIS_MSIX_TABLE_OPERATION"
 - "NDIS_MSIX_TABLE_OPERATION"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
- ndis.h
api_name:
- NDIS_MSIX_TABLE_OPERATION
product:
- Windows
targetos: Windows
req.typenames: NDIS_MSIX_TABLE_OPERATION, *PNDIS_MSIX_TABLE_OPERATION
---

# _NDIS_MSIX_TABLE_CONFIG enumeration


## -description


The NDIS_MSIX_TABLE_OPERATION enumeration identifies the type of MSI-X configuration
  operation.


## -enum-fields




### -field NdisMSIXTableConfigSetTableEntry

The MSI-X table entry should be mapped to an MSI-X message that the bus driver allocated to the
     device.


### -field NdisMSIXTableConfigMaskTableEntry

The interrupts from an MSI-X table entry source should be masked.


### -field NdisMSIXTableConfigUnmaskTableEntry

The interrupts from an MSI-X table entry source should be unmasked.


### -field NdisMSIXTableConfigMax

The number of enumeration values in NDIS_MSIX_TABLE_OPERATION.


## -remarks



The NDIS_MSIX_TABLE_OPERATION enumeration is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_msix_config_parameters">
    NDIS_MSIX_CONFIG_PARAMETERS</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_msix_config_parameters">NDIS_MSIX_CONFIG_PARAMETERS</a>
 

 

