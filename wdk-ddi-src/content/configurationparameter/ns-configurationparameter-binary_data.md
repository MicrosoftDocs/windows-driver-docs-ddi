---
UID: NS:configurationparameter.BINARY_DATA
tech.root: netvista
title: BINARY_DATA
ms.date: 07/22/2025
targetos: Windows
description: The BINARY_DATA structure contains the binary data of a named entry in the registry.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: configurationparameter.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: BINARY_DATA
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - configurationparameter.h
api_name:
 - BINARY_DATA
f1_keywords:
 - BINARY_DATA
 - configurationparameter/BINARY_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - BINARY_DATA
---

# BINARY_DATA structure

## -description

The BINARY_DATA structure contains the binary data of a named entry in the registry.

## -struct-fields

### -field Length

The length, in bytes, of the data that the 
     <b>Buffer</b> member points to.

### -field Buffer

Pointer to a buffer containing the binary data.

## -remarks

The BINARY_DATA structure is used in the 
    <b>ParameterData</b> member of the 
    <a href="/windows-hardware/drivers/ddi/configurationparameter/ns-configurationparameter-_ndis_configuration_parameter">
    NDIS_CONFIGURATION_PARAMETER</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/configurationparameter/ns-configurationparameter-_ndis_configuration_parameter">NDIS_CONFIGURATION_PARAMETER</a>



