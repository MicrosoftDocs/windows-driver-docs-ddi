---
UID: NS:ucmmanager._UCM_CONNECTOR_TYPEC_CONFIG
title: _UCM_CONNECTOR_TYPEC_CONFIG (ucmmanager.h)
description: Describes the configuration options for a Type-C connector.
old-location: buses\ucm_connector_type_c_config.htm
tech.root: usbref
ms.assetid: F3C17CD8-F423-46E7-891F-E428235CEF3D
ms.date: 05/07/2018
keywords: ["_UCM_CONNECTOR_TYPEC_CONFIG structure"]
ms.keywords: "*PUCM_CONNECTOR_TYPEC_CONFIG, PUCM_CONNECTOR_TYPEC_CONFIG, PUCM_CONNECTOR_TYPEC_CONFIG structure pointer [Buses], UCM_CONNECTOR_TYPEC_CONFIG, UCM_CONNECTOR_TYPEC_CONFIG structure [Buses], _UCM_CONNECTOR_TYPEC_CONFIG, buses.ucm_connector_type_c_config, ucmmanager/PUCM_CONNECTOR_TYPEC_CONFIG, ucmmanager/UCM_CONNECTOR_TYPEC_CONFIG"
f1_keywords:
 - "ucmmanager/UCM_CONNECTOR_TYPEC_CONFIG"
 - "UCM_CONNECTOR_TYPEC_CONFIG"
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
- UCM_CONNECTOR_TYPEC_CONFIG
product:
- Windows
targetos: Windows
req.typenames: UCM_CONNECTOR_TYPEC_CONFIG, *PUCM_CONNECTOR_TYPEC_CONFIG
---

# _UCM_CONNECTOR_TYPEC_CONFIG structure


## -description


Describes the configuration options for a Type-C connector. 


## -struct-fields




### -field Size

Size of the <b>UCM_CONNECTOR_TYPEC_CONFIG</b> structure. 


### -field IsSupported

TRUE indicates a Type-C connector. FALSE, otherwise.  is supported. 


### -field SupportedOperatingModes

Indicates the supported operating mode of the connector. This value is a bitwise OR of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_typec_operating_mode">UCM_TYPEC_OPERATING_MODE</a>-typed flags.


### -field SupportedPowerSourcingCapabilities

Indicates the supported power source capabilities of the connector. This value is a bitwise OR of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_typec_current">UCM_TYPEC_CURRENT</a>-typed flags.


### -field AudioAccessoryCapable

Indicates whether the connector is capable of detecting a USB Type-C analog input as 3.5 mm audio jack.


### -field EvtSetDataRole

A pointer to the client driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nc-ucmmanager-evt_ucm_connector_set_data_role">EVT_UCM_CONNECTOR_SET_DATA_ROLE</a> callback function.


## -remarks



Initialize this structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_connector_typec_config_init">UCM_CONNECTOR_TYPEC_CONFIG_INIT</a>. An initialized <b>UCM_CONNECTOR_TYPEC_CONFIG</b> structure is an input parameter value to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a> that is used by Policy Manager to create a connector object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>
 

 

