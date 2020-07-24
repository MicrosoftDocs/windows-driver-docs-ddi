---
UID: NS:ucmmanager._UCM_CONNECTOR_PD_CONFIG
title: _UCM_CONNECTOR_PD_CONFIG (ucmmanager.h)
description: Describes the Power Delivery 2.0 capabilities of the connector.
old-location: buses\ucm_connector_pd_config.htm
tech.root: usbref
ms.assetid: 9DE2AF2D-D6B5-4FC4-8871-246F3661980F
ms.date: 05/07/2018
keywords: ["_UCM_CONNECTOR_PD_CONFIG structure"]
ms.keywords: "*PUCM_CONNECTOR_PD_CONFIG, PUCM_CONNECTOR_PD_CONFIG, PUCM_CONNECTOR_PD_CONFIG structure pointer [Buses], UCM_CONNECTOR_PD_CONFIG, UCM_CONNECTOR_PD_CONFIG structure [Buses], _UCM_CONNECTOR_PD_CONFIG, buses.ucm_connector_pd_config, ucmmanager/PUCM_CONNECTOR_PD_CONFIG, ucmmanager/UCM_CONNECTOR_PD_CONFIG"
f1_keywords:
 - "ucmmanager/UCM_CONNECTOR_PD_CONFIG"
 - "UCM_CONNECTOR_PD_CONFIG"
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
- UCM_CONNECTOR_PD_CONFIG
targetos: Windows
req.typenames: UCM_CONNECTOR_PD_CONFIG, *PUCM_CONNECTOR_PD_CONFIG
---

# _UCM_CONNECTOR_PD_CONFIG structure


## -description


Describes the Power Delivery 2.0 capabilities of the connector.


## -struct-fields




### -field Size

Size of the <b>UCM_CONNECTOR_PD_CONFIG</b> structure. 


### -field IsSupported

If TRUE, a PD role is supported. (Default).

If FALSE, a PD role is not supported.


### -field SupportedPowerRoles

Indicates the operating mode of the connector. This value is a bitwise OR of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_power_role">UCM_POWER_ROLE</a>-typed flags.


### -field EvtSetPowerRole

A pointer to the Policy Manager's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nc-ucmmanager-evt_ucm_connector_set_power_role">EVT_UCM_CONNECTOR_SET_POWER_ROLE</a> event callback.


## -remarks



Initialize this structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_connector_pd_config_init">UCM_CONNECTOR_PD_CONFIG_INIT</a>. An initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_typec_config">UCM_CONNECTOR_TYPEC_CONFIG</a> structure is set to the <b>PdConfig</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_config">UCM_CONNECTOR_CONFIG</a> structure, which is an input parameter value to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a> that is called by Policy Manager to create a connector object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>
 

 

