---
UID: NS:usbpmapi._USBPM_CONNECTOR_STATE
title: _USBPM_CONNECTOR_STATE (usbpmapi.h)
description: Describes the state of a connector.
ms.assetid: 5430de09-aae7-49da-ae7f-50fd996e4386
ms.date: 09/30/2018
ms.topic: struct
f1_keywords:
 - "usbpmapi/_USBPM_CONNECTOR_STATE"
tech.root: usbref
ms.keywords: _USBPM_CONNECTOR_STATE, USBPM_CONNECTOR_STATE, *PUSBPM_CONNECTOR_STATE, 
req.header: usbpmapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: USBPM_CONNECTOR_STATE, *PUSBPM_CONNECTOR_STATE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- usbpmapi.h
api_name: 
- _USBPM_CONNECTOR_STATE
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _USBPM_CONNECTOR_STATE structure

## -description
Describes the state of a connector. This structure is used in the [**UsbPm_RetrieveConnectorState**](nf-usbpmapi-usbpm_retrieveconnectorstate.md) call. The client driver must initialize this structure by calling [**USBPM_CONNECTOR_STATE_INIT**](C:\wdk-ddi\wdk-ddi-src\content\usbpmapi\nf-usbpmapi-usbpm_connector_state_init.md).

## -struct-fields

### -field ConnectorHandle
A handle to this connector.
 
### -field ChangeToken
The change token number of this state. This value is changed for every connector state change. 
 
### -field Attached
Indicates whether this connector is attached.
 
### -field AttachCount
Indicates the number of attache events that have occurred on this connector. If client driver sees the transition from one “Attached” state to another “Attached” state but with different “AttachCount”, it indicates two attaches and with two different port partners.

### -field Partner
The type of the port partner, defined in the [**USBC_PARTNER**](../usbctypes/ne-usbctypes-_usbc_partner.md) enumeration.
 
### -field CurrentAdvertisement
The amount of Type-C current advertised. 

### -field PdConnState
Indicates the PD contract state over the connection on this connector.
 
### -field Rdo
The PD Request Data Object that has sent to the port partner of this connector. See [**USBC_PD_REQUEST_DATA_OBJECT**](../usbctypes/ns-usbctypes-_usbc_pd_request_data_object.md).
 
### -field DataRole
Indicates the USB Type-C data role of the connector, defined in the [**USBC_DATA_ROLE**](../usbctypes/ne-usbctypes-_usbc_data_role.md) enumeration.

### -field PowerRole
Indicates the USB Type-C power role of the connector, defined in the [**USBC_POWER_ROLE**](../usbctypes/ne-usbctypes-_usbc_power_role.md) enumeration.
 
### -field SourceCapsCount
The number of power data objects in the source caps array.
 
### -field SourceCaps
The source capabilities of the connector. See [**USBC_PD_POWER_DATA_OBJECT**](../usbctypes/ns-usbctypes-_usbc_pd_power_data_object.md).
 
### -field SinkCapsCount
The number of power data objects in the corresponding array.

### -field SinkCaps
The sink capability of the connector. See [**USBC_PD_POWER_DATA_OBJECT**](../usbctypes/ns-usbctypes-_usbc_pd_power_data_object.md).
 
### -field PartnerSourceCapsCount
The number of power data objects in the corresponding array.
 
### -field PartnerSourceCaps
The source capabilities of the port partner in the corresponding array. See [**USBC_PD_POWER_DATA_OBJECT**](../usbctypes/ns-usbctypes-_usbc_pd_power_data_object.md).
### -field PdAlternateModesEnteredCount
The number of alternate modes entered. 

## -remarks


## -see-also
