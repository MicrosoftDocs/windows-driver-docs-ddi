---
UID: NS:61883._CMP_GET_PLUG_STATE
title: _CMP_GET_PLUG_STATE (61883.h)
description: This structure is used in getting the state of a plug.
old-location: ieee\cmp_get_plug_state.htm
tech.root: IEEE
ms.assetid: 76BC179A-7484-433C-8467-B13BA7008B90
ms.date: 02/15/2018
ms.keywords: "*PCMP_GET_PLUG_STATE, 61883/CMP_GET_PLUG_STATE, 61883/PCMP_GET_PLUG_STATE, CMP_GET_PLUG_STATE, CMP_GET_PLUG_STATE structure [Buses], IEEE.cmp_get_plug_state, PCMP_GET_PLUG_STATE, PCMP_GET_PLUG_STATE structure pointer [Buses], _CMP_GET_PLUG_STATE"
ms.topic: struct
req.header: 61883.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
- 61883.h
api_name:
- CMP_GET_PLUG_STATE
product:
- Windows
targetos: Windows
req.typenames: CMP_GET_PLUG_STATE, *PCMP_GET_PLUG_STATE
---

# _CMP_GET_PLUG_STATE structure


## -description


This structure is used in getting the state of a plug.The  request retrieves state information for the specified plug, including its current connections and bus data format. Plug state is volatile and can change unexpectedly. 


## -struct-fields




### -field hPlug

On input, the handle of the plug to retrieve state information.


### -field State

On output, the state of the plug. Can be one of the following:

CMP_PLUG_STATE_IDLE 

CMP_PLUG_STATE_READY 

CMP_PLUG_STATE_SUSPENDED 

CMP_PLUG_STATE_ACTIVE 


### -field DataRate

On output, the data rate of the plug. Can be one of the following: 

CMP_SPEED_S100 

CMP_SPEED_S200 

CMP_SPEED_S400 


### -field Payload

On output, the payload size for the plug.


### -field BC_Connections

On output, the number of broadcast connections associated with the plug.


### -field PP_Connections

On output, the number of point-to-point connections associated with the plug.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

