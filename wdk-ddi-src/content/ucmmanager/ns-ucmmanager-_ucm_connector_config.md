---
UID: NS:ucmmanager._UCM_CONNECTOR_CONFIG
title: "_UCM_CONNECTOR_CONFIG"
author: windows-driver-content
description: Describes the configuration options for a Type-C connector object. An initialized UCM_MANAGER_CONFIG structure is an input parameter value to UcmInitializeDevice.
old-location: buses\ucm_connector_config.htm
tech.root: usbref
ms.assetid: 8FE8B7E2-1CC0-4540-86D5-A09BA249D62A
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: "*PUCM_CONNECTOR_CONFIG, PUCM_CONNECTOR_CONFIG, PUCM_CONNECTOR_CONFIG structure pointer [Buses], UCM_CONNECTOR_CONFIG, UCM_CONNECTOR_CONFIG structure [Buses], _UCM_CONNECTOR_CONFIG, buses.ucm_connector_config, ucmmanager/PUCM_CONNECTOR_CONFIG, ucmmanager/UCM_CONNECTOR_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucmmanager.h
api_name:
-	UCM_CONNECTOR_CONFIG
product:
- Windows
targetos: Windows
req.typenames: UCM_CONNECTOR_CONFIG, *PUCM_CONNECTOR_CONFIG
---

# _UCM_CONNECTOR_CONFIG structure


## -description


Describes the configuration options for a Type-C connector object. An initialized <a href="https://msdn.microsoft.com/library/windows/hardware/mt187932">UCM_MANAGER_CONFIG</a> structure is an input parameter value to   <a href="https://msdn.microsoft.com/library/windows/hardware/mt187920">UcmInitializeDevice</a>.


## -struct-fields




### -field Size

Size of the <b>UCM_CONNECTOR_CONFIG</b> structure. 


### -field ConnectorId

Connector identifier. 


### -field TypeCConfig

A pointer to an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/mt187930">UCM_CONNECTOR_TYPEC_CONFIG</a> structure that contains the configuration options for the connector. 


### -field PdConfig

 




#### - PDConfig

A pointer to an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/mt187924">UCM_CONNECTOR_PD_CONFIG</a> structure that contains the power roles supported by the connector. 


## -remarks



Initialize this structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187923">UCM_CONNECTOR_CONFIG_INIT</a>. An initialized <b>UCM_CONNECTOR_CONFIG</b> structure is an input parameter value to <a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a> that is used by the client driver to create a connector object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>
 

 

