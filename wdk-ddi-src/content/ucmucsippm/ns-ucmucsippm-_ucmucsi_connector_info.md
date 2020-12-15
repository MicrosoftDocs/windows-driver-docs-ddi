---
UID: NS:ucmucsippm._UCMUCSI_CONNECTOR_INFO
title: _UCMUCSI_CONNECTOR_INFO (ucmucsippm.h)
tech.root: usbref
description: Stores information about connectors that cannot be obtained by sending UCSI commands such as “Get Connector Capability”.
ms.date: 09/30/2018
keywords: ["UCMUCSI_CONNECTOR_INFO structure"]
ms.keywords: _UCMUCSI_CONNECTOR_INFO, UCMUCSI_CONNECTOR_INFO, *PUCMUCSI_CONNECTOR_INFO,
req.header: ucmucsippm.h
req.include-header: UcmUcsiCx.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: UCMUCSI_CONNECTOR_INFO, *PUCMUCSI_CONNECTOR_INFO
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _UCMUCSI_CONNECTOR_INFO
 - ucmucsippm/_UCMUCSI_CONNECTOR_INFO
 - PUCMUCSI_CONNECTOR_INFO
 - ucmucsippm/PUCMUCSI_CONNECTOR_INFO
 - UCMUCSI_CONNECTOR_INFO
 - ucmucsippm/UCMUCSI_CONNECTOR_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ucmucsippm.h
api_name:
 - _UCMUCSI_CONNECTOR_INFO
---

# _UCMUCSI_CONNECTOR_INFO structure


## -description

Stores information about connectors that cannot be obtained by sending UCSI commands such as GetConnectorCapability. Initialize this structure by calling [**UCMUCSI_CONNECTOR_INFO_INIT**](nf-ucmucsippm-ucmucsi_connector_info_init.md). This structure is used in the [**UcmUcsiConnectorCollectionAddConnector**](nf-ucmucsippm-ucmucsiconnectorcollectionaddconnector.md) call.

## -struct-fields

### -field Size

Size of this structure.

### -field ConnectorId

Connector ID that maps a USB Type-C connector to USB port.

## -remarks

## -see-also

