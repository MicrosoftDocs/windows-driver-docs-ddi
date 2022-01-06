---
UID: NF:ucmmanager.UcmConnectorDataDirectionChanged
title: UcmConnectorDataDirectionChanged function (ucmmanager.h)
description: Notifies the USB connector manager framework extension (UcmCx) with the new data role of a change in data role.
old-location: buses\ucmconnectordatadirectionchanged.htm
tech.root: usbref
ms.date: 01/05/2022
keywords: ["UcmConnectorDataDirectionChanged function"]
ms.keywords: UcmConnectorDataDirectionChanged, UcmConnectorDataDirectionChanged method [Buses], buses.ucmconnectordatadirectionchanged, ucmmanager/UcmConnectorDataDirectionChanged
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
 - UcmConnectorDataDirectionChanged
 - ucmmanager/UcmConnectorDataDirectionChanged
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - UcmCxstub.lib
 - UcmCxstub.dll
api_name:
 - UcmConnectorDataDirectionChanged
---

# UcmConnectorDataDirectionChanged function

## -description

Notifies the USB connector manager framework extension (UcmCx) with the new data role  of a change in data role.

## -parameters

### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to [UcmConnectorCreate](/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate).

### -param Success [in]

Used to indicate failure of a data-role swap that was initiated by UcmCx using [EVT_UCM_CONNECTOR_SET_DATA_ROLE](/windows-hardware/drivers/ddi/ucmmanager/nc-ucmmanager-evt_ucm_connector_set_data_role).

If TRUE, the operation was successful. FALSE, otherwise.

### -param CurrentDataRole [in]

A [UCM_TYPEC_PARTNER](/windows-hardware/drivers/ddi/ucmtypes/ne-ucmtypes-_ucm_typec_partner) value that indicates the new data role.

## -remarks

**UcmConnectorDataDirectionChanged** returns STATUS_SUCCESS if the operation succeeds. Otherwise, this inline function can return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) value.

If the connector partner is attached, UcmCx updates the data role of the partner depending on the *CurrentDataRole* value. For example, if the client driver changes the data role to **UcmTypeCPortStateUfp**, UcmCx updates the role of the connector partner to **UcmTypeCPortStateDfp**.

UcmCx can change the data role of a connector, and invokes [EVT_UCM_CONNECTOR_SET_DATA_ROLE](/windows-hardware/drivers/ddi/ucmmanager/nc-ucmmanager-evt_ucm_connector_set_data_role). In response to that call, the client should perform the DR_Swap operation, and indicate success/failure of the operation by calling  **UcmConnectorDataDirectionChanged**.

Alternatively, the client driver might choose to perform a role-swap autonomously, or the partner might perform a role-swap. In either case, when the role-swap has completed, the driver must report the new role to UcmCx using **UcmConnectorDataDirectionChanged**.

## -see-also

- [UcmConnectorCreate](/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate)
