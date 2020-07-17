---
UID: NS:ucmmanager._UCM_CONNECTOR_CONFIG
title: _UCM_CONNECTOR_CONFIG (ucmmanager.h)
description: Describes the configuration options for a Type-C connector object. An initialized UCM_MANAGER_CONFIG structure is an input parameter value to UcmInitializeDevice.
old-location: buses\ucm_connector_config.htm
tech.root: usbref
ms.assetid: 8FE8B7E2-1CC0-4540-86D5-A09BA249D62A
ms.date: 05/07/2018
keywords: ["_UCM_CONNECTOR_CONFIG structure"]
ms.keywords: "*PUCM_CONNECTOR_CONFIG, PUCM_CONNECTOR_CONFIG, PUCM_CONNECTOR_CONFIG structure pointer [Buses], UCM_CONNECTOR_CONFIG, UCM_CONNECTOR_CONFIG structure [Buses], _UCM_CONNECTOR_CONFIG, buses.ucm_connector_config, ucmmanager/PUCM_CONNECTOR_CONFIG, ucmmanager/UCM_CONNECTOR_CONFIG"
f1_keywords:
 - "ucmmanager/UCM_CONNECTOR_CONFIG"
 - "UCM_CONNECTOR_CONFIG"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ucmmanager.h
api_name:
- UCM_CONNECTOR_CONFIG
product:
- Windows
targetos: Windows
req.typenames: UCM_CONNECTOR_CONFIG, *PUCM_CONNECTOR_CONFIG
---

# _UCM_CONNECTOR_CONFIG structure


## -description


Describes the configuration options for a Type-C connector object. An initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_manager_config">UCM_MANAGER_CONFIG</a> structure is an input parameter value to   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucminitializedevice">UcmInitializeDevice</a>.


## -struct-fields




### -field Size

Size of the <b>UCM_CONNECTOR_CONFIG</b> structure. 


### -field ConnectorId

Connector identifier. 


### -field TypeCConfig

A pointer to an initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_typec_config">UCM_CONNECTOR_TYPEC_CONFIG</a> structure that contains the configuration options for the connector. 


### -field PdConfig

 




#### - PDConfig

A pointer to an initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_pd_config">UCM_CONNECTOR_PD_CONFIG</a> structure that contains the power roles supported by the connector. 


## -remarks



Initialize this structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_connector_config_init">UCM_CONNECTOR_CONFIG_INIT</a>. An initialized <b>UCM_CONNECTOR_CONFIG</b> structure is an input parameter value to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a> that is used by the client driver to create a connector object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>
 

 

