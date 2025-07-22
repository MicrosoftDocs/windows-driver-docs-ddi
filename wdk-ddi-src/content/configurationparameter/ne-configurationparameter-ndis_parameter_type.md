---
UID: NE:configurationparameter._NDIS_PARAMETER_TYPE
tech.root: netvista
title: NDIS_PARAMETER_TYPE
ms.date: 07/22/2025
targetos: Windows
description: The NDIS_PARAMETER_TYPE enumeration type identifies the type of a registry entry.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: configurationparameter.h
req.include-header: ndis.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers in Windows Vista. Supported for NDIS   5.1 drivers in Windows XP.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: NDIS_PARAMETER_TYPE, *PNDIS_PARAMETER_TYPE
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - configurationparameter.h
api_name:
 - _NDIS_PARAMETER_TYPE
 - PNDIS_PARAMETER_TYPE
 - NDIS_PARAMETER_TYPE
f1_keywords:
 - _NDIS_PARAMETER_TYPE
 - configurationparameter/_NDIS_PARAMETER_TYPE
 - PNDIS_PARAMETER_TYPE
 - configurationparameter/PNDIS_PARAMETER_TYPE
 - NDIS_PARAMETER_TYPE
 - configurationparameter/NDIS_PARAMETER_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_PARAMETER_TYPE
---

# _NDIS_PARAMETER_TYPE enumeration


## -description

The NDIS_PARAMETER_TYPE enumeration type identifies the type of a registry entry.

## -enum-fields

### -field NdisParameterInteger

An integer in decimal notation.

### -field NdisParameterHexInteger

An integer in hexadecimal notation.

### -field NdisParameterString

A string of type NDIS_STRING.

### -field NdisParameterMultiString

A multistring parameter of the REG_MULTI_SZ type.

### -field NdisParameterBinary

A binary value of type REG_BINARY.

## -remarks

The NDIS_PARAMETER_TYPE enumeration type is used in the 
    <a href="/windows-hardware/drivers/ddi/configurationparameter/ns-configurationparameter-_ndis_configuration_parameter">
    NDIS_CONFIGURATION_PARAMETER</a> structure and in the 
    <i>ParameterType</i> parameter of the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/configurationparameter/ns-configurationparameter-_ndis_configuration_parameter">NDIS_CONFIGURATION_PARAMETER</a>

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a>

