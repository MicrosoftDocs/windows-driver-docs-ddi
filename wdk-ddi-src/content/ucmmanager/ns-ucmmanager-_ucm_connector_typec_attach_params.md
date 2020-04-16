---
UID: NS:ucmmanager._UCM_CONNECTOR_TYPEC_ATTACH_PARAMS
title: _UCM_CONNECTOR_TYPEC_ATTACH_PARAMS (ucmmanager.h)
description: Describes the partner that is currently attached to the connector.
old-location: buses\ucm_connector_typec_attach_params.htm
tech.root: usbref
ms.assetid: D1D4B9D8-0BBF-4592-9EC8-ED294D6D0C90
ms.date: 05/07/2018
keywords: ["_UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure"]
ms.keywords: "*PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS, PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS, PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure pointer [Buses], UCM_CONNECTOR_TYPEC_ATTACH_PARAMS, UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure [Buses], _UCM_CONNECTOR_TYPEC_ATTACH_PARAMS, buses.ucm_connector_typec_attach_params, ucmmanager/PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS, ucmmanager/UCM_CONNECTOR_TYPEC_ATTACH_PARAMS"
f1_keywords:
 - "ucmmanager/UCM_CONNECTOR_TYPEC_ATTACH_PARAMS"
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
- UCM_CONNECTOR_TYPEC_ATTACH_PARAMS
product:
- Windows
targetos: Windows
req.typenames: UCM_CONNECTOR_TYPEC_ATTACH_PARAMS, *PUCM_CONNECTOR_TYPEC_ATTACH_PARAMS
---

# _UCM_CONNECTOR_TYPEC_ATTACH_PARAMS structure


## -description


Describes the partner that is currently attached to the connector.


## -struct-fields




### -field Size

Size of the <b>UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</b> structure. 


### -field Partner

 


### -field CurrentAdvertisement

Power sourcing capabilities of: the partner port when <b>PortPartnerType</b> is <b>UcmTypeCPortStateDfp</b>; the local port when <b>PortPartnerType</b> is not <b>UcmTypeCPortStateDfp</b>. 


### -field ChargingState

Optional. Charging state of the port indicated by one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_charging_state">UCM_CHARGING_STATE</a>-typed flags. 


#### - PortPartnerType

The type of partner attached to the connector, indicated by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_typec_partner">UCM_TYPEC_PARTNER</a> value.


## -remarks



Initialize this structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_connector_typec_attach_params_init">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT</a>. An initialized <b>UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</b> structure is an input parameter value to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectortypecattach">UcmConnectorTypeCAttach</a> that is used by the client driver to notify UcmCx about the Attached state of the port.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectortypecattach">UcmConnectorTypeCAttach</a>
 

 

