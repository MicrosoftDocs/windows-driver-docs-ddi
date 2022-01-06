---
UID: NS:ucmmanager._UCM_CONNECTOR_CONFIG
title: _UCM_CONNECTOR_CONFIG (ucmmanager.h)
description: Describes the configuration options for a Type-C connector object. An initialized UCM_MANAGER_CONFIG structure is an input parameter value to UcmInitializeDevice.
old-location: buses\ucm_connector_config.htm
tech.root: usbref
ms.date: 01/05/2022
keywords: ["UCM_CONNECTOR_CONFIG structure"]
ms.keywords: "*PUCM_CONNECTOR_CONFIG, PUCM_CONNECTOR_CONFIG, PUCM_CONNECTOR_CONFIG structure pointer [Buses], UCM_CONNECTOR_CONFIG, UCM_CONNECTOR_CONFIG structure [Buses], _UCM_CONNECTOR_CONFIG, buses.ucm_connector_config, ucmmanager/PUCM_CONNECTOR_CONFIG, ucmmanager/UCM_CONNECTOR_CONFIG"
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
req.typenames: UCM_CONNECTOR_CONFIG, *PUCM_CONNECTOR_CONFIG
f1_keywords:
 - _UCM_CONNECTOR_CONFIG
 - ucmmanager/_UCM_CONNECTOR_CONFIG
 - PUCM_CONNECTOR_CONFIG
 - ucmmanager/PUCM_CONNECTOR_CONFIG
 - UCM_CONNECTOR_CONFIG
 - ucmmanager/UCM_CONNECTOR_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucmmanager.h
api_name:
 - _UCM_CONNECTOR_CONFIG
 - PUCM_CONNECTOR_CONFIG
 - UCM_CONNECTOR_CONFIG
---

# _UCM_CONNECTOR_CONFIG structure

## -description

Describes the configuration options for a Type-C connector object. An initialized [UCM_MANAGER_CONFIG](/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_manager_config) structure is an input parameter value to [UcmInitializeDevice](/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucminitializedevice).

## -struct-fields

### -field Size

Size of the **UCM_CONNECTOR_CONFIG** structure.

### -field ConnectorId

Connector identifier.

### -field TypeCConfig

A pointer to an initialized [UCM_CONNECTOR_TYPEC_CONFIG](/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_typec_config) structure that contains the configuration options for the connector.

### -field PdConfig

A pointer to an initialized [UCM_CONNECTOR_PD_CONFIG](/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_pd_config) structure that contains the power roles supported by the connector.

## -remarks

Initialize this structure by calling [UCM_CONNECTOR_CONFIG_INIT](/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_connector_config_init). An initialized **UCM_CONNECTOR_CONFIG** structure is an input parameter value to [UcmConnectorCreate](/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate) that is used by the client driver to create a connector object.

## -see-also

- [UcmConnectorCreate](/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate)
