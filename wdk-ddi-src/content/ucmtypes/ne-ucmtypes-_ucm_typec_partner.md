---
UID: NE:ucmtypes._UCM_TYPEC_PARTNER
title: _UCM_TYPEC_PARTNER (ucmtypes.h)
description: Defines the state of the Type-C connector.
old-location: buses\ucm_type_c_port_state.htm
tech.root: usbref
ms.date: 01/05/2022
keywords: ["UCM_TYPEC_PARTNER enumeration"]
ms.keywords: UCM_TYPEC_PARTNER, UCM_TYPEC_PARTNER enumeration [Buses], UcmTypeCPartnerStateAudioAccessory, UcmTypeCPartnerStateDebugAccessory, UcmTypeCPartnerStateDfp, UcmTypeCPartnerStateInvalid, UcmTypeCPartnerStatePoweredCableNoUfp, UcmTypeCPartnerStatePoweredCableWithUfp, UcmTypeCPartnerStateUfp, _UCM_TYPEC_PARTNER, buses.ucm_type_c_port_state, ucmtypes/UCM_TYPEC_PARTNER, ucmtypes/UcmTypeCPartnerStateAudioAccessory, ucmtypes/UcmTypeCPartnerStateDebugAccessory, ucmtypes/UcmTypeCPartnerStateDfp, ucmtypes/UcmTypeCPartnerStateInvalid, ucmtypes/UcmTypeCPartnerStatePoweredCableNoUfp, ucmtypes/UcmTypeCPartnerStatePoweredCableWithUfp, ucmtypes/UcmTypeCPartnerStateUfp
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
req.typenames: UCM_TYPEC_PARTNER
f1_keywords:
 - _UCM_TYPEC_PARTNER
 - ucmtypes/_UCM_TYPEC_PARTNER
 - UCM_TYPEC_PARTNER
 - ucmtypes/UCM_TYPEC_PARTNER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucmtypes.h
api_name:
 - _UCM_TYPEC_PARTNER
 - UCM_TYPEC_PARTNER
---

# _UCM_TYPEC_PARTNER enumeration

## -description

Defines the state of the Type-C connector.

## -enum-fields

### -field UcmTypeCPartnerInvalid

The partner port state is invalid.

### -field UcmTypeCPartnerUfp

The partner is an upstream facing port (UFP).

### -field UcmTypeCPartnerDfp

The partner is a downstream facing port (DFP).

### -field UcmTypeCPartnerPoweredCableNoUfp

The partner is a powered cable that requires VConn, that currently does not have a UFP attached on the other end.

### -field UcmTypeCPartnerPoweredCableWithUfp

The partner is a powered and upstream facing.

### -field UcmTypeCPartnerAudioAccessory

The partner is used as an audio accessory.

### -field UcmTypeCPartnerDebugAccessory

The partner is a debug accessory.

## -see-also

- [UCM_CONNECTOR_TYPEC_ATTACH_PARAMS](../ucmmanager/ns-ucmmanager-_ucm_connector_typec_attach_params.md)
- [UcmConnectorTypeCAttach](../ucmmanager/nf-ucmmanager-ucmconnectortypecattach.md)