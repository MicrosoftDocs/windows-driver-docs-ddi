---
UID: NS:ucmmanager._UCM_CONNECTOR_TYPEC_ATTACH_PARAMS
title: _UCM_CONNECTOR_TYPEC_ATTACH_PARAMS (ucmmanager.h)
description: Describes the partner that is currently attached to the connector.
old-location: buses\ucm_connector_typec_attach_params.htm
tech.root: usbref
ms.date: 01/05/2022
keywords: ["UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure"]
ms.keywords: "*PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS, PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS, PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure pointer [Buses], UCM_CONNECTOR_TYPEC_ATTACH_PARAMS, UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure [Buses], _UCM_CONNECTOR_TYPEC_ATTACH_PARAMS, buses.ucm_connector_typec_attach_params, ucmmanager/PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS, ucmmanager/UCM_CONNECTOR_TYPEC_ATTACH_PARAMS"
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
req.typenames: UCM_CONNECTOR_TYPEC_ATTACH_PARAMS, *PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS
f1_keywords:
 - _UCM_CONNECTOR_TYPEC_ATTACH_PARAMS
 - ucmmanager/_UCM_CONNECTOR_TYPEC_ATTACH_PARAMS
 - PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS
 - ucmmanager/PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS
 - UCM_CONNECTOR_TYPEC_ATTACH_PARAMS
 - ucmmanager/UCM_CONNECTOR_TYPEC_ATTACH_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucmmanager.h
api_name:
 - _UCM_CONNECTOR_TYPEC_ATTACH_PARAMS
 - PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS
 - UCM_CONNECTOR_TYPEC_ATTACH_PARAMS
---

# _UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure

## -description

Describes the partner that is currently attached to the connector.

## -struct-fields

### -field Size

Size of the **UCM_CONNECTOR_TYPEC_ATTACH_PARAMS** structure.

### -field Partner

The type of partner attached to the connector, indicated by a [UCM_TYPEC_PARTNER](../ucmtypes/ne-ucmtypes-_ucm_typec_partner.md) value.

### -field CurrentAdvertisement

Power sourcing capabilities of: the partner port when **PortPartnerType** is **UcmTypeCPortStateDfp**; the local port when **PortPartnerType** is not **UcmTypeCPortStateDfp**.

### -field ChargingState

Optional. Charging state of the port indicated by one of the [UCM_CHARGING_STATE](../ucmtypes/ne-ucmtypes-_ucm_charging_state.md)-typed flags.

## -remarks

Initialize this structure by calling [UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT](./nf-ucmmanager-ucm_connector_typec_attach_params_init.md). An initialized **UCM_CONNECTOR_TYPEC_ATTACH_PARAMS** structure is an input parameter value to [UcmConnectorTypeCAttach](./nf-ucmmanager-ucmconnectortypecattach.md) that is used by the client driver to notify UcmCx about the Attached state of the port.

## -see-also

- [UcmConnectorTypeCAttach](./nf-ucmmanager-ucmconnectortypecattach.md)