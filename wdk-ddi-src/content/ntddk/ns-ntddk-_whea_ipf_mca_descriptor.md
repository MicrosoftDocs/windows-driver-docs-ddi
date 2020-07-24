---
UID: NS:ntddk._WHEA_IPF_MCA_DESCRIPTOR
title: _WHEA_IPF_MCA_DESCRIPTOR (ntddk.h)
description: The WHEA_IPF_MCA_DESCRIPTOR structure describes a machine check abort (MCA) error source for an Itanium processor.
old-location: whea\whea_ipf_mca_descriptor.htm
tech.root: whea
ms.assetid: 2961a568-32e0-4c48-b5bc-5cfb0f78272d
ms.date: 02/20/2018
keywords: ["_WHEA_IPF_MCA_DESCRIPTOR structure"]
ms.keywords: "*PWHEA_IPF_MCA_DESCRIPTOR, PWHEA_IPF_MCA_DESCRIPTOR, PWHEA_IPF_MCA_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_IPF_MCA_DESCRIPTOR, WHEA_IPF_MCA_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_IPF_MCA_DESCRIPTOR, ntddk/PWHEA_IPF_MCA_DESCRIPTOR, ntddk/WHEA_IPF_MCA_DESCRIPTOR, whea.whea_ipf_mca_descriptor, whearef_855b78be-e404-4bc0-a9fa-a0f03e61151d.xml"
f1_keywords:
 - "ntddk/WHEA_IPF_MCA_DESCRIPTOR"
 - "WHEA_IPF_MCA_DESCRIPTOR"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
- ntddk.h
api_name:
- WHEA_IPF_MCA_DESCRIPTOR
targetos: Windows
req.typenames: WHEA_IPF_MCA_DESCRIPTOR, *PWHEA_IPF_MCA_DESCRIPTOR
---

# _WHEA_IPF_MCA_DESCRIPTOR structure


## -description


The WHEA_IPF_MCA_DESCRIPTOR structure describes a machine check abort (MCA) error source for an Itanium processor.


## -struct-fields




### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_IPFMCA.


### -field Enabled

A Boolean value that indicates if the error source is enabled.


### -field Reserved

Reserved for system use.


## -remarks



A WHEA_IPF_MCA_DESCRIPTOR structure is contained within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a>
 

 

