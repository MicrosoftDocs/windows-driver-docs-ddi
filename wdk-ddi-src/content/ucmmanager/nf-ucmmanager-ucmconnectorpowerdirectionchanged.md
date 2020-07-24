---
UID: NF:ucmmanager.UcmConnectorPowerDirectionChanged
title: UcmConnectorPowerDirectionChanged function (ucmmanager.h)
description: Notifies the USB connector manager framework extension (UcmCx) with the new power role of the partner connector.
old-location: buses\ucmconnectorpowerdirectionchanged.htm
tech.root: usbref
ms.assetid: D1DB20DF-C0FD-4215-8227-CBBB18AF8BE3
ms.date: 05/07/2018
keywords: ["UcmConnectorPowerDirectionChanged function"]
ms.keywords: UcmConnectorPowerDirectionChanged, UcmConnectorPowerDirectionChanged method [Buses], buses.ucmconnectorpowerdirectionchanged, ucmmanager/UcmConnectorPowerDirectionChanged
f1_keywords:
 - "ucmmanager/UcmConnectorPowerDirectionChanged"
 - "UcmConnectorPowerDirectionChanged"
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
req.lib: UcmCxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- UcmCxstub.lib
- UcmCxstub.dll
api_name:
- UcmConnectorPowerDirectionChanged
targetos: Windows
req.typenames: 
---

# UcmConnectorPowerDirectionChanged function


## -description


Notifies the USB connector manager framework extension (UcmCx) with the new power role  of the partner connector.


## -parameters




### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>.


### -param Success [in]

Used to indicate failure of a power-role swap that was initiated by UcmCx using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nc-ucmmanager-evt_ucm_connector_set_power_role">EVT_UCM_CONNECTOR_SET_POWER_ROLE</a>. 

If TRUE, the operation was successful. FALSE, otherwise.


### -param CurrentPowerRole [in]

One of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_power_role">UCM_POWER_ROLE</a>-typed flags that indicates the new data role. 


## -returns



<b>UcmConnectorPowerDirectionChanged</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> value. 




## -remarks



If the connector partner is attached, UcmCx updates the power role of the partner depending on the <i> CurrentPowerRole</i> value. 

UcmCx can change the power role of a connector, and invokes <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nc-ucmmanager-evt_ucm_connector_set_power_role">EVT_UCM_CONNECTOR_SET_POWER_ROLE</a>. In response to that call, the client should perform the PR_Swap operation, and indicate success/failure of the operation by calling  <b>UcmConnectorPowerDirectionChanged</b>.

Alternatively, the client driver might choose to perform a role-swap autonomously, or the partner might perform a role-swap. In either case, when the role-swap has completed, the driver must report the new role to UcmCx using <b>UcmConnectorPowerDirectionChanged</b>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>
 

 

