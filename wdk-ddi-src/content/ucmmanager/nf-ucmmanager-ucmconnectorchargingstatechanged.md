---
UID: NF:ucmmanager.UcmConnectorChargingStateChanged
title: UcmConnectorChargingStateChanged function (ucmmanager.h)
description: Notifies the USB connector manager framework extension (UcmCx) with the updated charging state of the partner connector.
old-location: buses\ucmconnectorchargingstatechanged.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UcmConnectorChargingStateChanged function"]
ms.keywords: UcmConnectorChargingStateChanged, UcmConnectorChargingStateChanged method [Buses], buses.ucmconnectorchargingstatechanged, ucmmanager/UcmConnectorChargingStateChanged
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UcmConnectorChargingStateChanged
 - ucmmanager/UcmConnectorChargingStateChanged
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - UcmCxstub.lib
 - UcmCxstub.dll
api_name:
 - UcmConnectorChargingStateChanged
---

# UcmConnectorChargingStateChanged function


## -description

Notifies the USB connector manager framework extension (UcmCx) with the updated charging state of the partner connector.

## -parameters

### -param Connector 

[in]
Handle to the connector object that the client driver received in the previous call to <a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>.

### -param ChargingState 

[in]
One of the <a href="/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_charging_state">UCM_CHARGING_STATE</a>-typed flags that indicates the new charging state.

## -returns

<b>UcmConnectorChargingStateChanged</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> value.

## -remarks

If the client driver determines that the charging state is non-optimal, it should report slow or trickle charging to UcmCx. Then, the operating system notifies the user of this condition.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>
