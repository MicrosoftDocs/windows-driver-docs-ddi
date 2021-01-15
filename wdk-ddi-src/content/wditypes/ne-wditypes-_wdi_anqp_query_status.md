---
UID: NE:wditypes._WDI_ANQP_QUERY_STATUS
title: _WDI_ANQP_QUERY_STATUS (wditypes.h)
description: The WDI_ANQP_QUERY_STATUS enumeration defines the Access Network Query Protocol (ANQP) query status values.
old-location: netvista\wdi_anqp_query_status.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_ANQP_QUERY_STATUS enumeration"]
ms.keywords: WDI_ANQP_QUERY_STATUS, WDI_ANQP_QUERY_STATUS enumeration [Network Drivers Starting with Windows Vista], WDI_ANQP_QUERY_STATUS_ACCESS_ISSUES, WDI_ANQP_QUERY_STATUS_ADVERTISEMENT_PROTOCOL_NOT_SUPPORTED_ON_REMOTE, WDI_ANQP_QUERY_STATUS_ADVERTISEMENT_SERVER_NOT_RESPONDING, WDI_ANQP_QUERY_STATUS_FAILURE, WDI_ANQP_QUERY_STATUS_GAS_PROTOCOL_FAILURE, WDI_ANQP_QUERY_STATUS_RESOURCES, WDI_ANQP_QUERY_STATUS_SUCCESS, WDI_ANQP_QUERY_STATUS_TIMED_OUT, _WDI_ANQP_QUERY_STATUS, netvista.wdi_anqp_query_status, netvista.wifi_anqp_query_status, wditypes/WDI_ANQP_QUERY_STATUS, wditypes/WDI_ANQP_QUERY_STATUS_ACCESS_ISSUES, wditypes/WDI_ANQP_QUERY_STATUS_ADVERTISEMENT_PROTOCOL_NOT_SUPPORTED_ON_REMOTE, wditypes/WDI_ANQP_QUERY_STATUS_ADVERTISEMENT_SERVER_NOT_RESPONDING, wditypes/WDI_ANQP_QUERY_STATUS_FAILURE, wditypes/WDI_ANQP_QUERY_STATUS_GAS_PROTOCOL_FAILURE, wditypes/WDI_ANQP_QUERY_STATUS_RESOURCES, wditypes/WDI_ANQP_QUERY_STATUS_SUCCESS, wditypes/WDI_ANQP_QUERY_STATUS_TIMED_OUT
req.header: wditypes.hpp
req.include-header: 
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
req.typenames: WDI_ANQP_QUERY_STATUS
f1_keywords:
 - _WDI_ANQP_QUERY_STATUS
 - wditypes/_WDI_ANQP_QUERY_STATUS
 - WDI_ANQP_QUERY_STATUS
 - wditypes/WDI_ANQP_QUERY_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_ANQP_QUERY_STATUS
 - WDI_ANQP_QUERY_STATUS
---

# _WDI_ANQP_QUERY_STATUS enumeration


## -description

The WDI_ANQP_QUERY_STATUS enumeration defines the Access Network Query Protocol (ANQP) query status values.

## -enum-fields

### -field WDI_ANQP_QUERY_STATUS_SUCCESS

Maps to SUCCESS.

### -field WDI_ANQP_QUERY_STATUS_FAILURE

The failure did not map to any of the other status codes.

### -field WDI_ANQP_QUERY_STATUS_TIMED_OUT

  Maps to GAS_QUERY_TIMEOUT. The STA timed out waiting for a GAS response.

### -field WDI_ANQP_QUERY_STATUS_RESOURCES

The operating system is unable to allocate sufficient resources to complete the request.

### -field WDI_ANQP_QUERY_STATUS_ADVERTISEMENT_PROTOCOL_NOT_SUPPORTED_ON_REMOTE

Maps to GAS_ADVERTISEMENT_PROTOCOL_NOT_SUPPORTED. The GAS advertisement protocol is not supported on the remote device.

### -field WDI_ANQP_QUERY_STATUS_GAS_PROTOCOL_FAILURE

Mapped for any of the following errors.

<ul>
<li>NO_OUTSTANDING_GAS_REQUEST</li>
<li>GAS_QUERY_RESPONSE_TOO_LARGE</li>
<li>TRANSMISSION_FAILURE</li>
</ul>

### -field WDI_ANQP_QUERY_STATUS_ADVERTISEMENT_SERVER_NOT_RESPONDING

Mapped for any of the following errors.

<ul>
<li>GAS_RESPONSE_NOT_RECEIVED_FROM_SERVER</li>
<li>GAS_QUERY_TIMEOUT</li>
<li>SERVER_UNREACHABLE</li>
</ul>

### -field WDI_ANQP_QUERY_STATUS_ACCESS_ISSUES

Mapped for any of the following errors.

<ul>
<li>REJECTED_HOME_WITH_SUGGESTED_CHANGES</li>
<li>REJECTED_FOR_SSP_PERMISSIONS</li>
<li>AP does not support unauthenticated access</li>
</ul>

