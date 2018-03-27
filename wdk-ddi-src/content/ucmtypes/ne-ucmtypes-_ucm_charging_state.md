---
UID: NE:ucmtypes._UCM_CHARGING_STATE
title: "_UCM_CHARGING_STATE"
author: windows-driver-content
description: Defines the charging state of a Type-C connector.
old-location: buses\ucm_charging_state.htm
old-project: usbref
ms.assetid: DDC3532A-0084-4C56-B540-C638AB7F7080
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCM_CHARGING_STATE, UCM_CHARGING_STATE, UCM_CHARGING_STATE enumeration [Buses], UcmChargingStateInvalid, UcmChargingStateNominalCharging, UcmChargingStateNotCharging, UcmChargingStateSlowCharging, UcmChargingStateTrickleCharging, _UCM_CHARGING_STATE, buses.ucm_charging_state, ucmtypes/ UcmChargingStateTrickleCharging, ucmtypes/UCM_CHARGING_STATE, ucmtypes/UcmChargingStateInvalid, ucmtypes/UcmChargingStateNominalCharging, ucmtypes/UcmChargingStateNotCharging, ucmtypes/UcmChargingStateSlowCharging"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucmtypes.h
api_name:
-	UCM_CHARGING_STATE
product: Windows
targetos: Windows
req.typenames: UCM_CHARGING_STATE, *PUCM_CHARGING_STATE
req.product: Windows 10 or later.
---

# _UCM_CHARGING_STATE enumeration


## -description


Defines the charging state of a Type-C connector.


## -enum-fields




### -field UcmChargingStateInvalid

Indicates the charging state is invalid.


### -field UcmChargingStateNotCharging

Indicates the port is not drawing a charge.


### -field UcmChargingStateNominalCharging

Indicates the port is drawing a nominal charge.


### -field UcmChargingStateSlowCharging

Indicates the port is drawing a slow charge.


### -field UcmChargingStateTrickleCharging

Indicates the port is drawing a trickle charge.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187926">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187928">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187911">UcmConnectorPdConnectionStateChanged</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187915">UcmConnectorTypeCAttach</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_CHARGING_STATE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

