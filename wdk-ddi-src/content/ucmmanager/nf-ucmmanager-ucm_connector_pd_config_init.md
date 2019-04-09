---
UID: NF:ucmmanager.UCM_CONNECTOR_PD_CONFIG_INIT
title: UCM_CONNECTOR_PD_CONFIG_INIT function (ucmmanager.h)
description: Initializes a UCM_CONNECTOR_PD_CONFIG structure.
old-location: buses\ucm_connector_pd_config_init.htm
tech.root: usbref
ms.assetid: 59663F6C-5C8E-4403-8097-7E6D9A075A60
ms.date: 05/07/2018
ms.keywords: UCM_CONNECTOR_PD_CONFIG_INIT, UCM_CONNECTOR_PD_CONFIG_INIT function [Buses], buses.ucm_connector_pd_config_init, ucmmanager/UCM_CONNECTOR_PD_CONFIG_INIT
ms.topic: function
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
- UCM_CONNECTOR_PD_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCM_CONNECTOR_PD_CONFIG_INIT function


## -description


Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187924">UCM_CONNECTOR_PD_CONFIG</a> structure.


## -parameters




### -param Config [out]

Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/mt187924">UCM_CONNECTOR_PD_CONFIG</a> structure to initialize.


### -param SupportedPowerRoles [in]

A bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/mt187944">UCM_POWER_ROLE</a>-typed flags.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>
 

 

