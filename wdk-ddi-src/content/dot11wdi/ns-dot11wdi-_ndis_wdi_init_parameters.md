---
UID: NS:dot11wdi._NDIS_WDI_INIT_PARAMETERS
title: _NDIS_WDI_INIT_PARAMETERS (dot11wdi.h)
description: The NDIS_WDI_INIT_PARAMETERS structure specifies the WDI functions provided by the operating system and called by the IHV WDI driver.
old-location: netvista\ndis_wdi_init_parameters.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WDI_INIT_PARAMETERS structure"]
ms.keywords: "*PNDIS_WDI_INIT_PARAMETERS, NDIS_WDI_INIT_PARAMETERS, NDIS_WDI_INIT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_WDI_INIT_PARAMETERS, PNDIS_WDI_INIT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WDI_INIT_PARAMETERS, dot11wdi/NDIS_WDI_INIT_PARAMETERS, dot11wdi/PNDIS_WDI_INIT_PARAMETERS, netvista.ndis_wdi_init_parameters"
req.header: dot11wdi.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
targetos: Windows
req.typenames: NDIS_WDI_INIT_PARAMETERS, *PNDIS_WDI_INIT_PARAMETERS
f1_keywords:
 - _NDIS_WDI_INIT_PARAMETERS
 - dot11wdi/_NDIS_WDI_INIT_PARAMETERS
 - PNDIS_WDI_INIT_PARAMETERS
 - dot11wdi/PNDIS_WDI_INIT_PARAMETERS
 - NDIS_WDI_INIT_PARAMETERS
 - dot11wdi/NDIS_WDI_INIT_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - NDIS_WDI_INIT_PARAMETERS
---

# _NDIS_WDI_INIT_PARAMETERS structure


## -description

The NDIS_WDI_INIT_PARAMETERS structure specifies the WDI functions provided by the operating system and called by the IHV WDI driver.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_WDI_INIT_PARAMETERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_WDI_INIT_PARAMETERS.
     

To indicate the version of the NDIS_WDI_INIT_PARAMETERS structure, set the 
     <b>Revision</b> member to the following value:





#### NDIS_OBJECT_TYPE_WDI_INIT_PARAMETERS_REVISION_1

Set the 
        <b>Size</b> member to NDIS_SIZEOF_WDI_INIT_PARAMETERS_REVISION_1.

### -field WdiVersion

The version of WDI used by the driver. Set this member to one of the following values:





#### WDI_VERSION_1_0

WDI version 1.0

### -field OpenAdapterCompleteHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_open_adapter_complete">NdisWdiOpenAdapterComplete</a> callback function.

### -field CloseAdapterCompleteHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_close_adapter_complete">NdisWdiCloseAdapterComplete</a> callback function.

### -field UeIdleNotificationConfirm

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_idle_notification_confirm">NdisWdiIdleNotificationConfirm</a> callback function.

### -field UeIdleNotificationComplete

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_idle_notification_complete">NdisWdiIdleNotificationComplete</a> callback function.
