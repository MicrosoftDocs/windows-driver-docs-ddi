---
UID: NS:dot11wdi._NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
title: _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS (dot11wdi.h)
description: The NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure defines the set of handlers that a WDI miniport driver must implement.
old-location: netvista\ndis_miniport_driver_wdi_characteristics.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure"]
ms.keywords: "*PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, dot11wdi/NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, dot11wdi/PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, netvista.ndis_miniport_driver_wdi_characteristics"
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
req.typenames: NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS, *PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
f1_keywords:
 - _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
 - dot11wdi/_NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
 - PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
 - dot11wdi/PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
 - NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
 - dot11wdi/NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dot11wdi.h
api_name:
 - _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
 - PNDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
 - NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS
---

# _NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure defines the set of handlers that a WDI miniport driver must implement. It is used by the IHV driver to register additional handlers for the control path and the full set of handlers for the data path.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_WDI_CHARACTERISTICS.
     

To indicate the version of the NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS structure, set the 
     <b>Revision</b> member to the following value:





#### NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS_REVISION_1

Set the 
        <b>Size</b> member to NDIS_SIZEOF_MINIPORT_WDI_CHARACTERISTICS_REVISION_1.

### -field WdiVersion

The version of WDI used by the driver. Set this member to one of the following values:





#### WDI_VERSION_LATEST

The latest WDI version



#### WDI_VERSION_1_0_1

WDI version 1.0.1



#### WDI_VERSION_1_0

WDI version 1.0

### -field AllocateAdapterHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_allocate_adapter">MiniportWdiAllocateAdapter</a> handler function.

### -field FreeAdapterHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_free_adapter">MiniportWdiFreeAdapter</a> handler function.

### -field OpenAdapterHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_open_adapter">MiniportWdiOpenAdapter</a> handler function.

### -field CloseAdapterHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_close_adapter">MiniportWdiCloseAdapter</a> handler function.

### -field StartOperationHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_start_adapter_operation">MiniportWdiStartOperation</a> handler function.

### -field StopOperationHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_stop_adapter_operation">MiniportWdiStopOperation</a> handler function.

### -field PostPauseHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_post_adapter_pause">MiniportWdiPostAdapterPause</a> handler function.

### -field PostRestartHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_post_adapter_restart">MiniportWdiPostAdapterRestart</a> handler function.

### -field HangDiagnoseHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_adapter_hang_diagnose">MiniportWdiAdapterHangDiagnose</a> handler function.

### -field TalTxRxInitializeHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a> handler function.

### -field TalTxRxDeinitializeHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_deinitialize">MiniportWdiTalTxRxDeinitialize</a> handler function.

### -field LeIdleNotificationHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_idle_notification">MiniportWdiIdleNotification</a> handler function.

### -field LeCancelIdleNotificationHandler

The entry point of the <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_cancel_idle_notification">MiniportWdiCancelIdleNotification</a> handler function.

