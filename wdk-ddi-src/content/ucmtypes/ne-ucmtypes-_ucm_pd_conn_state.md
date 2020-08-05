---
UID: NE:ucmtypes._UCM_PD_CONN_STATE
title: _UCM_PD_CONN_STATE (ucmtypes.h)
description: Defines power delivery (PD) negotiation states of a Type-C port.
old-location: buses\ucm_pd_conn_state.htm
tech.root: usbref
ms.assetid: 7D146DDF-58A5-40C2-BF21-AF785DC7DB18
ms.date: 05/07/2018
keywords: ["UCM_PD_CONN_STATE enumeration"]
ms.keywords: UCM_PD_CONN_STATE, UCM_PD_CONN_STATE enumeration [Buses], UcmPdConnStateInvalid, UcmPdConnStateNegotiationFailed, UcmPdConnStateNegotiationSucceeded, UcmPdConnStateNotSupported, _UCM_PD_CONN_STATE, buses.ucm_pd_conn_state, ucmtypes/UCM_PD_CONN_STATE, ucmtypes/UcmPdConnStateInvalid, ucmtypes/UcmPdConnStateNegotiationFailed, ucmtypes/UcmPdConnStateNegotiationSucceeded, ucmtypes/UcmPdConnStateNotSupported
f1_keywords:
 - "ucmtypes/UCM_PD_CONN_STATE"
 - "UCM_PD_CONN_STATE"
req.header: ucmtypes.h
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
- Ucmtypes.h
api_name:
- UCM_PD_CONN_STATE
targetos: Windows
req.typenames: UCM_PD_CONN_STATE
---

# _UCM_PD_CONN_STATE enumeration


## -description


Defines power delivery (PD) negotiation states of a Type-C port.


## -enum-fields




### -field UcmPdConnStateInvalid

Indicates the PD negotiation state is invalid.


### -field UcmPdConnStateNotSupported

Indicates a PD connection is not supported. 


### -field UcmPdConnStateNegotiationFailed

Indicates the PD negotiation failed.


### -field UcmPdConnStateNegotiationSucceeded

Indicates the PD negotiation succeeded.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorpdconnectionstatechanged">UcmConnectorPdConnectionStateChanged</a>
 

 

