---
UID: NF:ucmmanager.UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT
title: UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT function (ucmmanager.h)
description: Initializes a UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure.
old-location: buses\ucm_connector_typec_attach_params_init.htm
tech.root: usbref
ms.assetid: C360556B-5A28-4FC3-9304-6000061A1D69
ms.date: 05/07/2018
ms.keywords: UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT, UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT function [Buses], buses.ucm_connector_typec_attach_params_init, ucmmanager/UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT
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
-	UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT function


## -description


Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187928">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a> structure.


## -parameters




### -param Params

<p>Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/Mt187928(v=VS.85).aspx"><b>UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</b></a> structure to initialize.</p>


### -param Partner

<p>A <a href="https://msdn.microsoft.com/library/Mt187947(v=VS.85).aspx"><b>UCM_TYPE_C_PORT_STATE</b></a>-typed flag that indicates the state of the partner port.</p>




## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187915">UcmConnectorTypeCAttach</a>
 

 

