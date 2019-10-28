---
UID: NF:ucmmanager.UCM_CONNECTOR_TYPEC_CONFIG_INIT
title: UCM_CONNECTOR_TYPEC_CONFIG_INIT function (ucmmanager.h)
description: Initializes the UCM_CONNECTOR_TYPEC_CONFIG structure.
old-location: buses\ucm_connector_type_c_config_init.htm
tech.root: usbref
ms.assetid: 10E155C2-907D-4D0E-87E9-A6B32E99D133
ms.date: 05/07/2018
ms.keywords: UCM_CONNECTOR_TYPEC_CONFIG_INIT, UCM_CONNECTOR_TYPE_C_CONFIG_INIT, UCM_CONNECTOR_TYPE_C_CONFIG_INIT function [Buses], buses.ucm_connector_type_c_config_init, ucmmanager/UCM_CONNECTOR_TYPE_C_CONFIG_INIT
ms.topic: function
f1_keywords:
 - "ucmmanager/UCM_CONNECTOR_TYPE_C_CONFIG_INIT"
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
- UCM_CONNECTOR_TYPE_C_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCM_CONNECTOR_TYPEC_CONFIG_INIT function


## -description


Initializes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_typec_config">UCM_CONNECTOR_TYPEC_CONFIG</a> structure.


## -parameters




### -param Config [out]

Pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_typec_config">UCM_CONNECTOR_TYPEC_CONFIG</a> structure to initialize.


### -param SupportedOperatingModes [in]

Indicates the operating mode of the connector. This value is a bitwise OR of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_typec_operating_mode">UCM_TYPEC_OPERATING_MODE</a>-typed flags.


### -param SupportedPowerSourcingCapabilities [in]

Indicates the power source capabilities of the connector. This value is a bitwise OR of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_typec_current">UCM_TYPEC_CURRENT</a>-typed flags.


## -returns



This function does not return a value.



