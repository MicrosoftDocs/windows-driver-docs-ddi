---
UID: NS:usbpmapi._USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
title: _USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS (usbpmapi.h)
description: Describes the parameters for the **UsbPm_AssignConnectorPowerLevel**.
ms.date: 09/30/2018
keywords: ["USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS structure"]
tech.root: usbref
ms.keywords: _USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS, USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS, *PUSBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS,
req.header: usbpmapi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS, *PUSBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
 - usbpmapi/_USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
 - PUSBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
 - usbpmapi/PUSBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
 - USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
 - usbpmapi/USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usbpmapi.h
api_name:
 - _USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
 - PUSBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
 - USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS
---

# _USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS structure


## -description

Describes the parameters for the [**UsbPm_AssignConnectorPowerLevel**](nf-usbpmapi-usbpm_assignconnectorpowerlevel.md) function. Initialize this structure by calling  [**USBPM_ASSIGN_CONNECTOR_POWER_LEVEL_PARAMS_INIT**](nf-usbpmapi-usbpm_assign_connector_power_level_params_init.md).

## -struct-fields

### -field PowerRole

The USB Type-C power role of the connector, defined in the [**USBC_POWER_ROLE**](../usbctypes/ne-usbctypes-_usbc_power_role.md) enumeration.

### -field Format

The power level format, defined in the [**USBPM_ASSIGN_POWER_LEVEL_PARAMS_FORMAT**](ne-usbpmapi-_usbpm_assign_power_level_params_format.md) enumeration.

### -field Ucsi

Description for the  USCI inner structure.

### -field Ucsi.MaximumPdPowerIn500mW

Maximum power in 500mW unit for the connector to provide/consume.

### -field Ucsi.MaximumTypeCCurrent

Maximum current for the connector to provide/consume, defined in the [**USBC_UCSI_SET_POWER_LEVEL_C_CURRENT**](../usbctypes/ne-usbctypes-_usbc_ucsi_set_power_level_c_current.md) enumeration.

### -field Rdo

Description for the  RDO inner structure.

### -field Rdo.Rdo

The PD Request Data Object that has sent to the port partner of this connector. See [**USBC_PD_REQUEST_DATA_OBJECT**](../usbctypes/ns-usbctypes-_usbc_pd_request_data_object.md).

## -remarks

## -see-also

