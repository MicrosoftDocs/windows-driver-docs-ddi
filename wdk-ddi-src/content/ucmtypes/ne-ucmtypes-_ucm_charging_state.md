---
UID: NE:ucmtypes._UCM_CHARGING_STATE
title: _UCM_CHARGING_STATE (ucmtypes.h)
description: Defines the charging state of a Type-C connector.
old-location: buses\ucm_charging_state.htm
tech.root: usbref
ms.assetid: DDC3532A-0084-4C56-B540-C638AB7F7080
ms.date: 05/07/2018
keywords: ["UCM_CHARGING_STATE enumeration"]
ms.keywords: "*PUCM_CHARGING_STATE, UCM_CHARGING_STATE, UCM_CHARGING_STATE enumeration [Buses], UcmChargingStateInvalid, UcmChargingStateNominalCharging, UcmChargingStateNotCharging, UcmChargingStateSlowCharging, UcmChargingStateTrickleCharging, _UCM_CHARGING_STATE, buses.ucm_charging_state, ucmtypes/ UcmChargingStateTrickleCharging, ucmtypes/UCM_CHARGING_STATE, ucmtypes/UcmChargingStateInvalid, ucmtypes/UcmChargingStateNominalCharging, ucmtypes/UcmChargingStateNotCharging, ucmtypes/UcmChargingStateSlowCharging"
req.header: ucmtypes.h
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
req.typenames: UCM_CHARGING_STATE, *PUCM_CHARGING_STATE
f1_keywords:
 - _UCM_CHARGING_STATE
 - ucmtypes/_UCM_CHARGING_STATE
 - PUCM_CHARGING_STATE
 - ucmtypes/PUCM_CHARGING_STATE
 - UCM_CHARGING_STATE
 - ucmtypes/UCM_CHARGING_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucmtypes.h
api_name:
 - UCM_CHARGING_STATE
---

# _UCM_CHARGING_STATE enumeration


## -description

Defines the charging state of a Type-C connector.

## -enum-fields

### -field UcmChargingStateInvalid

Indicates the charging state is invalid.

### -field UcmChargingStateNotCharging

Indicates the port is not drawing a charge.

### -field UcmChargingStateNominalCharging

Indicates the port is drawing a nominal charge.

### -field UcmChargingStateSlowCharging

Indicates the port is drawing a slow charge.

### -field UcmChargingStateTrickleCharging

Indicates the port is drawing a trickle charge.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_pd_conn_state_changed_params">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_typec_attach_params">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorpdconnectionstatechanged">UcmConnectorPdConnectionStateChanged</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectortypecattach">UcmConnectorTypeCAttach</a>

