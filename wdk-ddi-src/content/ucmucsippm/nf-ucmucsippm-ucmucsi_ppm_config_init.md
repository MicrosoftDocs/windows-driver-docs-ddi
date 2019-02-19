---
UID: NF:ucmucsippm.UCMUCSI_PPM_CONFIG_INIT
title: UCMUCSI_PPM_CONFIG_INIT function (ucmucsippm.h)
tech.root: usbref
description: Initializes a [**UCMUCSI_PPM_CONFIG**](ns-ucmucsippm-ucmucsi_ppm_config.md) structure.
ms.assetid: 3e8ee8c9-22e6-42dd-9299-b33f1d9b68f9
ms.date: 09/30/2018
ms.topic: function
ms.keywords: UCMUCSI_PPM_CONFIG_INIT
req.header: ucmucsippm.h
req.include-header: UcmUcsiCx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ucmucsippm.h
api_name: 
-	UCMUCSI_PPM_CONFIG_INIT
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# UCMUCSI_PPM_CONFIG_INIT function


## -description

Initializes a [**UCMUCSI_PPM_CONFIG**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmucsippm/ns-ucmucsippm-_ucmucsi_ppm_config) structure.

## -parameters

### -param Config
A pointer to a [**UCMUCSI_PPM_CONFIG**](ns-ucmucsippm-_ucmucsi_ppm_config.md) structure to initialize.

### -param CollectionObject
The handle to the connector collection object that the client driver retrieved in a previous call to [**UcmUcsiConnectorCollectionCreate**](nf-ucmucsippm-ucmucsiconnectorcollectioncreate.md).

## -returns
This function returns VOID.

## -remarks

## -see-also
[**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md)
[**UcmUcsiConnectorCollectionCreate**](nf-ucmucsippm-ucmucsiconnectorcollectioncreate.md)
