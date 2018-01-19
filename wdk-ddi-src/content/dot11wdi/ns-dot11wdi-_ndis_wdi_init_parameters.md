---
UID: NS:dot11wdi._NDIS_WDI_INIT_PARAMETERS
title: _NDIS_WDI_INIT_PARAMETERS
author: windows-driver-content
description: The NDIS_WDI_INIT_PARAMETERS structure specifies the WDI functions provided by the operating system and called by the IHV WDI driver.
old-location: netvista\ndis_wdi_init_parameters.htm
old-project: netvista
ms.assetid: 871D266C-55DF-4113-9714-92AB129303E5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_WDI_INIT_PARAMETERS, NDIS_WDI_INIT_PARAMETERS, *PNDIS_WDI_INIT_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WDI_INIT_PARAMETERS
req.alt-loc: dot11wdi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: NDIS_WDI_INIT_PARAMETERS, *PNDIS_WDI_INIT_PARAMETERS
---

# _NDIS_WDI_INIT_PARAMETERS structure



## -description
The NDIS_WDI_INIT_PARAMETERS structure specifies the WDI functions provided by the operating system and called by the IHV WDI driver.



## -syntax

````
typedef struct _NDIS_WDI_INIT_PARAMETERS {
  NDIS_OBJECT_HEADER                          Header;
  ULONG                                       WdiVersion;
  NDIS_WDI_OPEN_ADAPTER_COMPLETE_HANDLER      OpenAdapterCompleteHandler;
  NDIS_WDI_CLOSE_ADAPTER_COMPLETE_HANDLER     CloseAdapterCompleteHandler;
  NDIS_WDI_IDLE_NOTIFICATION_CONFIRM_HANDLER  UeIdleNotificationConfirm;
  NDIS_WDI_IDLE_NOTIFICATION_COMPLETE_HANDLER UeIdleNotificationComplete;
} NDIS_WDI_INIT_PARAMETERS, *PNDIS_WDI_INIT_PARAMETERS;
````


## -struct-fields

### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_WDI_INIT_PARAMETERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_WDI_INIT_PARAMETERS.
     

To indicate the version of the NDIS_WDI_INIT_PARAMETERS structure, set the 
     <b>Revision</b> member to the following value:




### -field NDIS_OBJECT_TYPE_WDI_INIT_PARAMETERS_REVISION_1

Set the 
        <b>Size</b> member to NDIS_SIZEOF_WDI_INIT_PARAMETERS_REVISION_1.

</dd>
</dl>

### -field WdiVersion

The version of WDI used by the driver. Set this member to one of the following values:




### -field WDI_VERSION_1_0

WDI version 1.0

</dd>
</dl>

### -field OpenAdapterCompleteHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_open_adapter_complete.md">NdisWdiOpenAdapterComplete</a> callback function.


### -field CloseAdapterCompleteHandler

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_close_adapter_complete.md">NdisWdiCloseAdapterComplete</a> callback function.


### -field UeIdleNotificationConfirm

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_idle_notification_confirm.md">NdisWdiIdleNotificationConfirm</a> callback function.


### -field UeIdleNotificationComplete

The entry point of the <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_idle_notification_complete.md">NdisWdiIdleNotificationComplete</a> callback function.


## -remarks
