---
UID: NS:dot11wdi._NDIS_WDI_INIT_PARAMETERS
title: "_NDIS_WDI_INIT_PARAMETERS"
author: windows-driver-content
description: The NDIS_WDI_INIT_PARAMETERS structure specifies the WDI functions provided by the operating system and called by the IHV WDI driver.
old-location: netvista\ndis_wdi_init_parameters.htm
old-project: netvista
ms.assetid: 871D266C-55DF-4113-9714-92AB129303E5
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_WDI_INIT_PARAMETERS, NDIS_WDI_INIT_PARAMETERS, NDIS_WDI_INIT_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_WDI_INIT_PARAMETERS, PNDIS_WDI_INIT_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WDI_INIT_PARAMETERS, dot11wdi/NDIS_WDI_INIT_PARAMETERS, dot11wdi/PNDIS_WDI_INIT_PARAMETERS, netvista.ndis_wdi_init_parameters"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dot11wdi.h
api_name:
-	NDIS_WDI_INIT_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_WDI_INIT_PARAMETERS, *PNDIS_WDI_INIT_PARAMETERS
---

# _NDIS_WDI_INIT_PARAMETERS structure


## -description


The NDIS_WDI_INIT_PARAMETERS structure specifies the WDI functions provided by the operating system and called by the IHV WDI driver.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
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

The entry point of the <a href="https://msdn.microsoft.com/FD6FF134-A8D7-433E-9353-88965E67749E">NdisWdiOpenAdapterComplete</a> callback function.


### -field CloseAdapterCompleteHandler

The entry point of the <a href="https://msdn.microsoft.com/42500F6F-8E97-454F-819F-8EA3785C0D04">NdisWdiCloseAdapterComplete</a> callback function.


### -field UeIdleNotificationConfirm

The entry point of the <a href="https://msdn.microsoft.com/39D070BE-FF6F-4EC8-A4E4-DF45C5089AA7">NdisWdiIdleNotificationConfirm</a> callback function.


### -field UeIdleNotificationComplete

The entry point of the <a href="https://msdn.microsoft.com/22622545-F92E-4FEE-8F5D-64EC792490C7">NdisWdiIdleNotificationComplete</a> callback function.

