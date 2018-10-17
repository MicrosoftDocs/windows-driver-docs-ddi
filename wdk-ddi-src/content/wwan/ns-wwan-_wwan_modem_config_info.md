---
UID: NS:wwan._WWAN_MODEM_CONFIG_INFO
title: "_WWAN_MODEM_CONFIG_INFO"
author: windows-driver-content
description: The WWAN_MODEM_CONFIG_INFO structure represents the modem's configuration information.
old-location: netvista\wwan_modem_config_info.htm
tech.root: netvista
ms.assetid: 14FBFA51-F4A5-417A-8905-241CEA543774
ms.date: 5/2/2018
ms.keywords: "*PWWAN_MODEM_CONFIG_INFO, PWWAN_MODEM_CONFIG_INFO, PWWAN_MODEM_CONFIG_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_MODEM_CONFIG_INFO, WWAN_MODEM_CONFIG_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_MODEM_CONFIG_INFO, netvista.wwan_modem_config_info, wwan/PWWAN_MODEM_CONFIG_INFO, wwan/WWAN_MODEM_CONFIG_INFO"
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_MODEM_CONFIG_INFO
product:
- Windows
targetos: Windows
req.typenames: WWAN_MODEM_CONFIG_INFO, *PWWAN_MODEM_CONFIG_INFO
---

# _WWAN_MODEM_CONFIG_INFO structure


## -description


The <b>WWAN_MODEM_CONFIG_INFO</b> structure represents the modem's configuration information.


## -struct-fields

### -field ConfigMode

The modem's configuration mode. For a list of defined values, see <a href="https://msdn.microsoft.com/1AA3EDCC-EB6E-4118-8081-CA1914140683">WWAN_MODEM_CONFIG_MODE</a>.

### -field ConfigState

The modem's configuration state. For a list of defined values, see [**WWAN_MODEM_CONFIG_STATE**](ne-wwan-_wwan_modem_config_state.md).

### -field ConfigReason

The reason for the modem's configuration state change. For a list of defined values, see [**WWAN_MODEM_CONFIG_REASON**](ne-wwan-_wwan_modem_config_reason.md).

### -field PreviousConfigID

A formatted [**WWAN_MODEM_CONFIG_ID**](ns-wwan-_wwan_modem_config_id.md) structure that represents the modem's previous configuration ID.

### -field CurrentConfigID

A formatted [**WWAN_MODEM_CONFIG_ID**](ns-wwan-_wwan_modem_config_id.md) structure that represents the modem's current configuration ID.

### -field IsCurrentConfigDefault

A DWORD value that indicates if the current configuration is the default configuration.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-modem-config-info">NDIS_STATUS_WWAN_MODEM_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/07C2BAED-157A-459C-B558-115C0091ECE5">NDIS_WWAN_MODEM_CONFIG_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-modem-config-info">OID_WWAN_MODEM_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/1AA3EDCC-EB6E-4118-8081-CA1914140683">WWAN_MODEM_CONFIG_MODE</a>



<a href="https://msdn.microsoft.com/3A13CFBC-DBB4-4BB1-ABA4-AB145AED07AA">WWAN_MODEM_CONFIG_STATUS</a>
 

 

