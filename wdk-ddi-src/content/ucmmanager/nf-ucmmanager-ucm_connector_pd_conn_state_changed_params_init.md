---
UID: NF:ucmmanager.UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT
title: UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function
author: windows-driver-content
description: Initializes a UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS structure.
old-location: buses\ucm_connector_pd_conn_state_changed_params_init.htm
old-project: usbref
ms.assetid: 177AF27E-3EBA-4D43-BAF2-11834784F762
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT, UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function [Buses], buses.ucm_connector_pd_conn_state_changed_params_init, ucmmanager/UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT
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
-	UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT
product: Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---

# UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT function


## -description


Initializes a <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_pd_conn_state_changed_params.md">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</a> structure.


## -syntax


````
void UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS_INIT(
  _Out_ PUCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS Params,
  _In_  UCM_PD_CONN_STATE                           PdConnState
);
````


## -parameters




### -param Params [out]

Pointer to a caller-allocated <a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_pd_conn_state_changed_params.md">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</a> structure to initialize.


### -param PdConnState [in]

A <a href="..\ucmtypes\ne-ucmtypes-_ucm_pd_conn_state.md">UCM_PD_CONN_STATE</a>-typed flag that indicates the connection state of the partner port.


## -returns



This function does not return a value.




## -see-also

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorpdconnectionstatechanged.md">UcmConnectorPdConnectionStateChanged</a>



 

 


