---
UID: NF:ucmmanager.UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT
title: UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function (ucmmanager.h)
description: Initializes a UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS structure.
old-location: buses\ucm_connector_pd_conn_state_changed_params_init.htm
tech.root: usbref
ms.assetid: 177AF27E-3EBA-4D43-BAF2-11834784F762
ms.date: 05/07/2018
ms.keywords: UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT, UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function [Buses], buses.ucm_connector_pd_conn_state_changed_params_init, ucmmanager/UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT
ms.topic: function
f1_keywords:
 - "ucmmanager/UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT"
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
- UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function


## -description


Initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmmanager/ns-ucmmanager-_ucm_connector_pd_conn_state_changed_params">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</a> structure.


## -parameters




### -param Params [out]

Pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmmanager/ns-ucmmanager-_ucm_connector_pd_conn_state_changed_params">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</a> structure to initialize.


### -param PdConnState [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtypes/ne-ucmtypes-_ucm_pd_conn_state">UCM_PD_CONN_STATE</a>-typed flag that indicates the connection state of the partner port.


## -returns



This function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmmanager/nf-ucmmanager-ucmconnectorpdconnectionstatechanged">UcmConnectorPdConnectionStateChanged</a>
 

 

