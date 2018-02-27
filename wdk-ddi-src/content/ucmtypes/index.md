---
UID: NA:ucmtypes
ms.assetid: 2e88b0b8-5fcc-378d-baf2-43106003f3b8
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ucmtypes.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Ucmtypes.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [UCM_PD_POWER_DATA_OBJECT_GET_TYPE function](nf-ucmtypes-ucm_pd_power_data_object_get_type.md) | Retrieves the type of Power Data Object from the UCM_PD_POWER_DATA_OBJECT structure. |
| [UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function](nf-ucmtypes-ucm_pd_power_data_object_init_battery.md) | Initializes a UCM_PD_POWER_DATA_OBJECT structure as a Battery Supply type Power Data Object. |
| [UCM_PD_POWER_DATA_OBJECT_INIT_FIXED function](nf-ucmtypes-ucm_pd_power_data_object_init_fixed.md) | Initializes a to the UCM_PD_POWER_DATA_OBJECT for a Fixed Supply type Power Data Object. |
| [UCM_PD_POWER_DATA_OBJECT_INIT_ULONG function](nf-ucmtypes-ucm_pd_power_data_object_init_ulong.md) | Initializes a UCM_PD_POWER_DATA_OBJECT structure by interpreting Power Data Object values and sets each field correctly. |
| [UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function](nf-ucmtypes-ucm_pd_power_data_object_init_variable_non_battery.md) | Initializes a UCM_PD_POWER_DATA_OBJECT structure as a Variable Supply Non Battery type Power Data Object. |
| [UCM_PD_REQUEST_DATA_OBJECT_INIT_ULONG function](nf-ucmtypes-ucm_pd_request_data_object_init_ulong.md) | Initializes a UCM_PD_REQUEST_DATA_OBJECT structure by interpreting Request Data Object values and sets each field correctly. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_UCM_PD_POWER_DATA_OBJECT structure](ns-ucmtypes-_ucm_pd_power_data_object.md) | Describes a Power Data Object. For information about these members, see the Power Delivery specification. |
| [_UCM_PD_REQUEST_DATA_OBJECT structure](ns-ucmtypes-_ucm_pd_request_data_object.md) | Describes a Request Data Object (RDO). For information about these members, see the Power Delivery specification. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_UCM_CHARGING_STATE enumeration](ne-ucmtypes-_ucm_charging_state.md) | Defines the charging state of a Type-C connector. |
| [_UCM_PD_CONN_STATE enumeration](ne-ucmtypes-_ucm_pd_conn_state.md) | Defines power delivery (PD) negotiation states of a Type-C port. |
| [_UCM_PD_POWER_DATA_OBJECT_TYPE enumeration](ne-ucmtypes-_ucm_pd_power_data_object_type.md) | Defines Power Data Object types. |
| [_UCM_POWER_ROLE enumeration](ne-ucmtypes-_ucm_power_role.md) | Defines power roles of USB Type-C connected devices. |
| [_UCM_TYPEC_CURRENT enumeration](ne-ucmtypes-_ucm_typec_current.md) | Defines different Type-C current levels, as defined in the Type-C specification. |
| [_UCM_TYPEC_OPERATING_MODE enumeration](ne-ucmtypes-_ucm_typec_operating_mode.md) | Defines operating modes of a USB Type-C connector. |
| [_UCM_TYPEC_PARTNER enumeration](ne-ucmtypes-_ucm_typec_partner.md) | Defines the state of the Type-C connector. |
