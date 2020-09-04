---
UID: NF:ucmmanager.UcmConnectorTypeCAttach
title: UcmConnectorTypeCAttach function (ucmmanager.h)
description: Notifies the USB connector manager framework extension (UcmCx) when a partner connector is attached.
old-location: buses\ucmconnectortypecattach.htm
tech.root: usbref
ms.assetid: D778E6B6-B245-41D5-B25B-1CF183146BA9
ms.date: 05/07/2018
keywords: ["UcmConnectorTypeCAttach function"]
ms.keywords: UcmConnectorTypeCAttach, UcmConnectorTypeCAttach method [Buses], buses.ucmconnectortypecattach, ucmmanager/UcmConnectorTypeCAttach
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
 - UcmConnectorTypeCAttach
 - ucmmanager/UcmConnectorTypeCAttach
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - UcmCxstub.lib
 - UcmCxstub.dll
api_name:
 - UcmConnectorTypeCAttach
---

# UcmConnectorTypeCAttach function


## -description

Notifies the USB connector manager framework extension (UcmCx) when a partner connector is attached.

## -parameters

### -param Connector 

[in]
Handle to the connector object that the client driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>.

### -param Params 

[in]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_typec_attach_params">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a> that has been initialized by  calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_connector_typec_attach_params_init">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT</a>.

## -returns

<b>UcmConnectorTypeCAttach</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> value.

## -remarks

When a connection to a partner connector is detected, the client driver calls this method to notify UcmCx with information about the partner connector. That information includes the connector role, down stream or upstream facing port, the amount of current connector can draw or deliver, and charging state. UcmCx uses that information to perform certain operations. For example, it may determine the role of the partner connector attached, and configure the USB controller in host or peripheral mode.


Typically, every  <b>UcmConnectorTypeCAttach</b> call has a subsequent <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectortypecdetach">UcmConnectorTypeCDetach</a> call to notify UcmCx when the partner connector is detached. However, when a powered cable without an upstream port is attached (indicated by <b>Params->PortPartnerType</b> set to <b>UcmTypeCPortStatePoweredCableNoUfp</b>). The client driver can call <b>UcmConnectorTypeCAttach</b> again when a connection is detected to the  upstream port to the powered cable.


#### Examples


```cpp
        UCM_CONNECTOR_TYPEC_ATTACH_PARAMS attachParams;

        UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT(
            &attachParams,
            UcmTypeCPortStateDfp);
        attachParams.CurrentAdvertisement = UcmTypeCCurrent1500mA;

        status = UcmConnectorTypeCAttach(
                    Connector,
                    &attachParams);
        if (!NT_SUCCESS(status))
        {
            TRACE_ERROR(
                "UcmConnectorTypeCAttach() failed with %!STATUS!.",
                status);
            goto Exit;
        }

        TRACE_INFO("UcmConnectorTypeCAttach() succeeded.");

```


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/ns-ucmmanager-_ucm_connector_typec_attach_params">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_connector_typec_attach_params_init">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucmconnectorcreate">UcmConnectorCreate</a>

