---
UID: NE:dot11wificxtypes._WDI_SAE_REQUEST_TYPE
tech.root: netvista
title: WDI_SAE_REQUEST_TYPE (dot11wificxtypes.h)
ms.date: 07/30/2021
targetos: Windows
description: The WDI_SAE_REQUEST_TYPE enum defines the type of SAE request frame to send to the BSSID.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_SAE_REQUEST_TYPE
 - WDI_SAE_REQUEST_TYPE
f1_keywords:
 - _WDI_SAE_REQUEST_TYPE
 - dot11wificxtypes/_WDI_SAE_REQUEST_TYPE
 - WDI_SAE_REQUEST_TYPE
 - dot11wificxtypes/WDI_SAE_REQUEST_TYPE
dev_langs:
 - c++
---

## -description

The **WDI_SAE_REQUEST_TYPE** enumeration defines the type of Simultaneous Authentication of Equals (SAE) request frame to send to the BSSID.

## -enum-fields

### -field WDI_SAE_REQUEST_TYPE_COMMIT_REQUEST:0

Send a Commit request. SAECommitRequest will be included.

### -field WDI_SAE_REQUEST_TYPE_CONFIRM_REQUEST:1

Send a Confirm request. SAEConfirmRequest will be included.

### -field WDI_SAE_REQUEST_TYPE_FAILURE:2

Request SAE authentication parameters failed. SAEStatus will be included.

### -field WDI_SAE_REQUEST_TYPE_SUCCESS:3

Request SAE authentication parameters succeeded.

### -field WDI_SAE_REQUEST_TYPE_COMMIT_REQUEST_H2E:4

Send a Commit Request using H2E. When Anti-Clogging token is specified, it will be encoded as Anti-Clogging Element instead of a field.

## -remarks

This enumeration is a value in the [OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/netcx/oid-wdi-set-sae-auth-params) command.

## -see-also

[WPA3-SAE Authentication](/windows-hardware/drivers/netcx/wpa3-sae-authentication)

[OID_WDI_SET_SAE_AUTH_PARAMS](/windows-hardware/drivers/network/oid-wdi-set-sae-auth-params)


