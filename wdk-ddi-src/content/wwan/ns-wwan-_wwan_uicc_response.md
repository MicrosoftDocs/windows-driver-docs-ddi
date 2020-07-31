---
UID: NS:wwan._WWAN_UICC_RESPONSE
title: _WWAN_UICC_RESPONSE (wwan.h)
description: The WWAN_UICC_RESPONSE structure describes a UICC response to a file read or write operation. 
tech.root: netvista
ms.assetid: 30E5B8D7-B104-469D-B3F0-7FE8C2BE295A
ms.date: 04/10/2019
keywords: ["_WWAN_UICC_RESPONSE structure"]
f1_keywords:
 - "wwan/_WWAN_UICC_RESPONSE"
 - "_WWAN_UICC_RESPONSE"
ms.keywords: _WWAN_UICC_RESPONSE, WWAN_UICC_RESPONSE, *PWWAN_UICC_RESPONSE, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: WWAN_UICC_RESPONSE, *PWWAN_UICC_RESPONSE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_UICC_RESPONSE
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_RESPONSE structure

## -description

The **WWAN_UICC_RESPONSE** structure describes a UICC response to a file read or write operation. 

## -struct-fields

### -field Version

The version number of the structure that follows. In Windows 10, version 1903, this version must be set to **1**.
 
### -field StatusWord1

A return parameter specific to the UICC command.

### -field StatusWord2

A return parameter specific to the UICC command.

### -field ResponseDataSize

The size of the response data, in bytes.

### -field ResponseData

Used only in Query (read) requests. The buffer containing the response data.

## -remarks

This structure is used in the [**NDIS_WWAN_UICC_RESPONSE**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_response.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_ACCESS_BINARY](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-access-binary)

[OID_WWAN_UICC_ACCESS_RECORD](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-access-record)

[**NDIS_WWAN_UICC_RESPONSE**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_response.md)
