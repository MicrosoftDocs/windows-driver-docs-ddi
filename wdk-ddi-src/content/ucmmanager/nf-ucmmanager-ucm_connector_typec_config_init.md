---
UID: NF:ucmmanager.UCM_CONNECTOR_TYPEC_CONFIG_INIT
title: UCM_CONNECTOR_TYPEC_CONFIG_INIT function
author: windows-driver-content
description: Initializes the UCM_CONNECTOR_TYPEC_CONFIG structure.
old-location: buses\ucm_connector_type_c_config_init.htm
old-project: usbref
ms.assetid: 10E155C2-907D-4D0E-87E9-A6B32E99D133
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UCM_CONNECTOR_TYPE_C_CONFIG_INIT, ucmmanager/UCM_CONNECTOR_TYPE_C_CONFIG_INIT, UCM_CONNECTOR_TYPEC_CONFIG_INIT, UCM_CONNECTOR_TYPE_C_CONFIG_INIT function [Buses], buses.ucm_connector_type_c_config_init
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ucmmanager.h
apiname: 
-	UCM_CONNECTOR_TYPE_C_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: *PPORT_DATA_1, PORT_DATA_1
req.product: Windows 10 or later.
---

# UCM_CONNECTOR_TYPEC_CONFIG_INIT function


## -description


Initializes the <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_typec_config.md">UCM_CONNECTOR_TYPEC_CONFIG</a> structure.


## -syntax


````
__inline
void UCM_CONNECTOR_TYPE_C_CONFIG_INIT(
  _Out_ PUCM_CONNECTOR_TYPEC_CONFIG Config,
  _In_  ULONG                       SupportedOperatingModes,
  _In_  ULONG                       SupportedPowerSourcingCapabilities
);
````


## -parameters




### -param Config [out]

Pointer to a caller-allocated <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_typec_config.md">UCM_CONNECTOR_TYPEC_CONFIG</a> structure to initialize.


### -param SupportedOperatingModes [in]

Indicates the operating mode of the connector. This value is a bitwise OR of <a href="..\ucmtypes\ne-ucmtypes-_ucm_typec_operating_mode.md">UCM_TYPEC_OPERATING_MODE</a>-typed flags.


### -param SupportedPowerSourcingCapabilities [in]

Indicates the power source capabilities of the connector. This value is a bitwise OR of <a href="..\ucmtypes\ne-ucmtypes-_ucm_typec_current.md">UCM_TYPEC_CURRENT</a>-typed flags.


## -returns


This function does not return a value.


