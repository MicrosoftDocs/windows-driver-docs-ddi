---
UID: NF:portcls.IMiniport.GetDescription
title: IMiniport::GetDescription (portcls.h)
description: The GetDescription method outputs a pointer to the miniport object's filter descriptor.
tech.root: audio
ms.assetid: 1e5d13a0-4052-4655-8e48-8cbe87ffc685
ms.date: 10/31/2018 
keywords: ["IMiniport::GetDescription"]
f1_keywords:
 - "portcls/IMiniport.GetDescription"
ms.keywords: IMiniport::GetDescription, GetDescription, IMiniport.GetDescription, IMiniport::GetDescription, IMiniport.GetDescription
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - portcls.h
api_name: 
 - IMiniport.GetDescription
product: 
 - Windows
targetos: Windows

---

# IMiniport::GetDescription


## -description

The GetDescription method outputs a pointer to the miniport object's filter descriptor.


## -parameters

### -param Description

Output pointer for the filter-descriptor pointer. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the filter descriptor. The filter descriptor is a structure of type PCFILTER_DESCRIPTOR.


## -returns
This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

The miniport driver's filter descriptor is a PCFILTER_DESCRIPTOR structure that describes the KS filter that the miniport driver implements. The structure contains descriptions of the filter's pins, nodes, connections, and properties.

## -see-also

[IMiniPort](nn-portcls-iminiport.md)
