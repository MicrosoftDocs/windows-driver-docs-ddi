---
UID: NS:ndis._NDIS_MSIX_CONFIG_PARAMETERS
title: "_NDIS_MSIX_CONFIG_PARAMETERS"
author: windows-driver-content
description: The NDIS_MSIX_CONFIG_PARAMETERS structure defines a requested configuration operation and specifies the parameters that are required for that particular operation.
old-location: netvista\ndis_msix_config_parameters.htm
tech.root: netvista
ms.assetid: 52c3238f-4d3a-4241-95bf-630e57e8a6e1
ms.date: 5/2/2018
ms.keywords: "*PNDIS_MSIX_CONFIG_PARAMETERS, NDIS_MSIX_CONFIG_PARAMETERS, NDIS_MSIX_CONFIG_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_MSIX_CONFIG_PARAMETERS, PNDIS_MSIX_CONFIG_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MSIX_CONFIG_PARAMETERS, ndis/NDIS_MSIX_CONFIG_PARAMETERS, ndis/PNDIS_MSIX_CONFIG_PARAMETERS, ndis_msix_ref_01a237b1-bb32-4aad-8552-b36b66141061.xml, netvista.ndis_msix_config_parameters"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_MSIX_CONFIG_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_MSIX_CONFIG_PARAMETERS, *PNDIS_MSIX_CONFIG_PARAMETERS
---

# _NDIS_MSIX_CONFIG_PARAMETERS structure


## -description


The NDIS_MSIX_CONFIG_PARAMETERS structure defines a requested configuration operation and specifies
  the parameters that are required for that particular operation.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MSIX_CONFIG_PARAMETERS structure. The miniport driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_MSIX_CONFIG_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MSIX_CONFIG_PARAMETERS_REVISION_1.


### -field ConfigOperation

The requested configuration operation for a MSI-X table entry. This operation is specified as one
     of the values from the 
     <a href="https://msdn.microsoft.com/7d1a4bb6-5db8-48b0-9be3-7468360951a1">
     NDIS_MSIX_TABLE_OPERATION</a> enumeration.


### -field TableEntry

The MSI-X table entry index.


### -field MessageNumber

The MSI-X message number that is assigned to the device. This value is required for the 
     <b>NdisMSIXTableConfigSetTableEntry</b> operation. This parameter is not used for the 
     <b>NdisMSIXTableConfigMaskTableEntry</b> or 
     <b>NdisMSIXTableConfigUnmaskTableEntry</b> operations.


## -remarks



To mask, unmask, or map MSI-X table entries, an NDIS driver passes the NDIS_MSIX_CONFIG_PARAMETERS
    structure to the 
    <a href="https://msdn.microsoft.com/93f94a42-bffb-4e4d-a560-b0da5d7d0019">
    NdisMConfigMSIXTableEntry</a> function. NDIS_MSIX_CONFIG_PARAMETERS defines a requested configuration
    operation and specifies the parameters that are required for that operation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566489">NDIS_MSIX_TABLE_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563566">NdisMConfigMSIXTableEntry</a>
 

 

