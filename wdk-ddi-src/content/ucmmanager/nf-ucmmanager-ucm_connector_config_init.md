---
UID: NF:ucmmanager.UCM_CONNECTOR_CONFIG_INIT
title: UCM_CONNECTOR_CONFIG_INIT function
author: windows-driver-content
description: Initializes a UCM_CONNECTOR_CONFIG structure.
old-location: buses\ucm_connector_config_init.htm
old-project: usbref
ms.assetid: F9076ED0-A9D2-441A-A084-941C05EF9CCA
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCM_CONNECTOR_CONFIG_INIT, UCM_CONNECTOR_CONFIG_INIT function [Buses], buses.ucm_connector_config_init, ucmmanager/UCM_CONNECTOR_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucmmanager.h
api_name:
-	UCM_CONNECTOR_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---

# UCM_CONNECTOR_CONFIG_INIT function


## -description


Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187922">UCM_CONNECTOR_CONFIG</a> structure.


## -parameters




### -param Config [out]

Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/mt187922">UCM_CONNECTOR_CONFIG</a> structure to initialize.


### -param ConnectorId [in]

The identifier to assign to the connector object. If there is only one connector, pass 0.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187932">UCM_MANAGER_CONFIG</a>
 

 

