---
UID: NF:ucmmanager.UCM_CONNECTOR_PD_CONFIG_INIT
title: UCM_CONNECTOR_PD_CONFIG_INIT function
author: windows-driver-content
description: Initializes a UCM_CONNECTOR_PD_CONFIG structure.
old-location: buses\ucm_connector_pd_config_init.htm
old-project: usbref
ms.assetid: 59663F6C-5C8E-4403-8097-7E6D9A075A60
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: UCM_CONNECTOR_PD_CONFIG_INIT function [Buses], buses.ucm_connector_pd_config_init, UCM_CONNECTOR_PD_CONFIG_INIT, ucmmanager/UCM_CONNECTOR_PD_CONFIG_INIT
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
-	UCM_CONNECTOR_PD_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---

# UCM_CONNECTOR_PD_CONFIG_INIT function


## -description


Initializes a <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_pd_config.md">UCM_CONNECTOR_PD_CONFIG</a> structure.


## -syntax


````
FORCEINLINE void UCM_CONNECTOR_PD_CONFIG_INIT(
  _Out_ PUCM_CONNECTOR_PD_CONFIG Config,
  _In_  ULONG                    SupportedPowerRoles
);
````


## -parameters




### -param Config [out]

Pointer to a caller-allocated <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_pd_config.md">UCM_CONNECTOR_PD_CONFIG</a> structure to initialize.


### -param SupportedPowerRoles [in]

A bitwise OR of <a href="..\ucmtypes\ne-ucmtypes-_ucm_power_role.md">UCM_POWER_ROLE</a>-typed flags.


## -returns



This function does not return a value.




## -see-also

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_CONNECTOR_PD_CONFIG_INIT function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

