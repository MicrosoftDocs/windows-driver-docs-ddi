---
UID: NE:ucmtypes._UCM_POWER_ROLE
title: _UCM_POWER_ROLE (ucmtypes.h)
description: Defines power roles of USB Type-C connected devices.
old-location: buses\ucm_power_role.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UCM_POWER_ROLE enumeration"]
ms.keywords: UCM_POWER_ROLE, UCM_POWER_ROLE enumeration [Buses], UcmPowerRoleInvalid, UcmPowerRoleSink, UcmPowerRoleSource, _UCM_POWER_ROLE, buses.ucm_power_role, ucmtypes/UCM_POWER_ROLE, ucmtypes/UcmPowerRoleInvalid, ucmtypes/UcmPowerRoleSink, ucmtypes/UcmPowerRoleSource
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
req.typenames: UCM_POWER_ROLE
f1_keywords:
 - _UCM_POWER_ROLE
 - ucmtypes/_UCM_POWER_ROLE
 - UCM_POWER_ROLE
 - ucmtypes/UCM_POWER_ROLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucmtypes.h
api_name:
 - UCM_POWER_ROLE
---

# _UCM_POWER_ROLE enumeration


## -description

Defines power roles of USB Type-C connected devices.

## -enum-fields

### -field UcmPowerRoleInvalid

Indicates the power role state is invalid.

### -field UcmPowerRoleSink

Indicates the power role is set to sink power.

### -field UcmPowerRoleSource

Indicates the power role is set to source power.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucmmanager/nc-ucmmanager-evt_ucm_connector_set_power_role">EVT_UCM_CONNECTOR_SET_POWER_ROLE</a>



<a href="/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_pd_config">UCM_CONNECTOR_PD_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorpowerdirectionchanged">UcmConnectorPowerDirectionChanged</a>
