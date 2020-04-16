---
UID: NS:ntddndis._NDIS_HD_SPLIT_PARAMETERS
title: _NDIS_HD_SPLIT_PARAMETERS (ntddndis.h)
description: The NDIS_HD_SPLIT_PARAMETERS structure defines the current header-data split settings of a miniport adapter.
old-location: netvista\ndis_hd_split_parameters.htm
tech.root: netvista
ms.assetid: 1cc76765-871e-4cd0-b927-b0b4d3d746b4
ms.date: 05/02/2018
keywords: ["_NDIS_HD_SPLIT_PARAMETERS structure"]
ms.keywords: "*PNDIS_HD_SPLIT_PARAMETERS, NDIS_HD_SPLIT_PARAMETERS, NDIS_HD_SPLIT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_HD_SPLIT_PARAMETERS, PNDIS_HD_SPLIT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_HD_SPLIT_PARAMETERS, header_data_split_ref_f7f3a3c4-4259-44a5-abce-fa393922f97d.xml, netvista.ndis_hd_split_parameters, ntddndis/NDIS_HD_SPLIT_PARAMETERS, ntddndis/PNDIS_HD_SPLIT_PARAMETERS"
f1_keywords:
 - "ntddndis/NDIS_HD_SPLIT_PARAMETERS"
req.header: ntddndis.h
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
- ntddndis.h
api_name:
- NDIS_HD_SPLIT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_HD_SPLIT_PARAMETERS, *PNDIS_HD_SPLIT_PARAMETERS
---

# _NDIS_HD_SPLIT_PARAMETERS structure


## -description


The NDIS_HD_SPLIT_PARAMETERS structure defines the current header-data split settings of a miniport
  adapter.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     provider characteristics structure (NDIS_HD_SPLIT_PARAMETERS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_ HD_SPLIT_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_HD_SPLIT_PARAMETERS_REVISION_1.


### -field HDSplitCombineFlags

A set of flags that specify the current header-data split settings of a miniport adapter. A
     protocol driver or user-mode application can specify a bitwise OR of the following flags:
     





#### NDIS_HD_SPLIT_COMBINE_ALL_HEADERS

The miniport adapter should combine split frames. If header-data split is enabled in the
       hardware, the miniport driver should combine the header and data before indicating the frame to
       NDIS.


## -remarks



The NDIS_HD_SPLIT_PARAMETERS structure is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-hd-split-parameters">OID_GEN_HD_SPLIT_PARAMETERS</a> OID set
    request to specify the current header-data split settings of a miniport adapter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-hd-split-parameters">OID_GEN_HD_SPLIT_PARAMETERS</a>
 

 

