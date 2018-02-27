---
UID: NA:ucmmanager
ms.assetid: 3e459ad2-db6c-372c-95bd-d836bce39752
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ucmmanager.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Ucmmanager.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [UCM_CONNECTOR_CONFIG_INIT function](nf-ucmmanager-ucm_connector_config_init.md) | Initializes a UCM_CONNECTOR_CONFIG structure. |
| [UCM_CONNECTOR_PD_CONFIG_INIT function](nf-ucmmanager-ucm_connector_pd_config_init.md) | Initializes a UCM_CONNECTOR_PD_CONFIG structure. |
| [UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function](nf-ucmmanager-ucm_connector_pd_conn_state_changed_params_init.md) | Initializes a UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS structure. |
| [UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT function](nf-ucmmanager-ucm_connector_typec_attach_params_init.md) | Initializes a UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure. |
| [UCM_CONNECTOR_TYPEC_CONFIG_INIT function](nf-ucmmanager-ucm_connector_typec_config_init.md) | Initializes the UCM_CONNECTOR_TYPEC_CONFIG structure. |
| [UCM_MANAGER_CONFIG_INIT function](nf-ucmmanager-ucm_manager_config_init.md) | Initializes a UCM_MANAGER_CONFIG structure. |
| [UcmConnectorChargingStateChanged function](nf-ucmmanager-ucmconnectorchargingstatechanged.md) | Notifies the USB connector manager framework extension (UcmCx) with the updated charging state of the partner connector. |
| [UcmConnectorCreate function](nf-ucmmanager-ucmconnectorcreate.md) | Creates a connector object. |
| [UcmConnectorDataDirectionChanged function](nf-ucmmanager-ucmconnectordatadirectionchanged.md) | Notifies the USB connector manager framework extension (UcmCx) with the new data role of a change in data role. |
| [UcmConnectorPdConnectionStateChanged function](nf-ucmmanager-ucmconnectorpdconnectionstatechanged.md) | Notifies the USB connector manager framework extension (UcmCx) with the connection capabilities of the currently negotiated PD contract (if any). |
| [UcmConnectorPdPartnerSourceCaps function](nf-ucmmanager-ucmconnectorpdpartnersourcecaps.md) | Notifies the USB connector manager framework extension (UcmCx) with the power source capabilities of the partner connector. |
| [UcmConnectorPdSourceCaps function](nf-ucmmanager-ucmconnectorpdsourcecaps.md) | Notifies the USB connector manager framework extension (UcmCx) with the power source capabilities of the connector. |
| [UcmConnectorPowerDirectionChanged function](nf-ucmmanager-ucmconnectorpowerdirectionchanged.md) | Notifies the USB connector manager framework extension (UcmCx) with the new power role of the partner connector. |
| [UcmConnectorTypeCAttach function](nf-ucmmanager-ucmconnectortypecattach.md) | Notifies the USB connector manager framework extension (UcmCx) when a partner connector is attached. |
| [UcmConnectorTypeCCurrentAdChanged function](nf-ucmmanager-ucmconnectortypeccurrentadchanged.md) | Notifies the USB connector manager framework extension (UcmCx) when the specified connector changes the current advertisement. Either the connector changes it (when it is DFP/Source), or the partner changed it (when it is UFP/Sink). |
| [UcmConnectorTypeCDetach function](nf-ucmmanager-ucmconnectortypecdetach.md) | Notifies the USB connector manager framework extension (UcmCx) when the partner connector detaches from the specified Type-C connector. |
| [UcmInitializeDevice function](nf-ucmmanager-ucminitializedevice.md) | Initializes the USB connector manager framework extension (UcmCx). |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_UCM_CONNECTOR_SET_DATA_ROLE callback](nc-ucmmanager-evt_ucm_connector_set_data_role.md) | The client driver's implementation of the EVT_UCM_CONNECTOR_SET_DATA_ROLE event callback function that swaps the data role of the connector to the specified role when attached to a partner connector. |
| [EVT_UCM_CONNECTOR_SET_POWER_ROLE callback](nc-ucmmanager-evt_ucm_connector_set_power_role.md) | The client driver's implementation of the EVT_UCM_CONNECTOR_SET_POWER_ROLE event callback function that sets the power role of the connector to the specified role when attached to a partner connector. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_UCM_CONNECTOR_CONFIG structure](ns-ucmmanager-_ucm_connector_config.md) | Describes the configuration options for a Type-C connector object. An initialized UCM_MANAGER_CONFIG structure is an input parameter value to UcmInitializeDevice. |
| [_UCM_CONNECTOR_PD_CONFIG structure](ns-ucmmanager-_ucm_connector_pd_config.md) | Describes the Power Delivery 2.0 capabilities of the connector. |
| [_UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS structure](ns-ucmmanager-_ucm_connector_pd_conn_state_changed_params.md) | Describes the parameters for PD connection changed event. |
| [_UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure](ns-ucmmanager-_ucm_connector_typec_attach_params.md) | Describes the partner that is currently attached to the connector. |
| [_UCM_CONNECTOR_TYPEC_CONFIG structure](ns-ucmmanager-_ucm_connector_typec_config.md) | Describes the configuration options for a Type-C connector. |
| [_UCM_MANAGER_CONFIG structure](ns-ucmmanager-_ucm_manager_config.md) | Describes the configuration options for the UCM Manager. An initialized UCM_MANAGER_CONFIG structure is an input parameter value to UcmInitializeDevice. |
