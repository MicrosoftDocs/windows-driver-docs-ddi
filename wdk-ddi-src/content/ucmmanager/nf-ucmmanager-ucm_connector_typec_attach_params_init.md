---
UID: NF:ucmmanager.UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT
title: UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT function (ucmmanager.h)
description: Initializes a UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure.
old-location: buses\ucm_connector_typec_attach_params_init.htm
tech.root: usbref
ms.assetid: C360556B-5A28-4FC3-9304-6000061A1D69
ms.date: 05/07/2018
ms.keywords: UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT, UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT function [Buses], buses.ucm_connector_typec_attach_params_init, ucmmanager/UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT
f1_keywords:
 - "ucmmanager/UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT"
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
- UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT function


## -description


Initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_typec_attach_params">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a> structure.


## -parameters




### -param Params

<p>Pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_typec_attach_params"><b>UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</b></a> structure to initialize.</p>


### -param Partner

<p>A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_typec_partner"><b>UCM_TYPE_C_PORT_STATE</b></a>-typed flag that indicates the state of the partner port.</p>




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectortypecattach">UcmConnectorTypeCAttach</a>
 

 

