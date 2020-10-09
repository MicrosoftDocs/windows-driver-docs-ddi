---
UID: NS:ndiswwan._NDIS_WWAN_UICC_ACCESS_BINARY
title: _NDIS_WWAN_UICC_ACCESS_BINARY (ndiswwan.h)
description: The NDIS_WWAN_UICC_ACCESS_BINARY structure describes information about a UICC binary file to read or to which to write.
tech.root: netvista
ms.assetid: E1DD7E29-CBD3-4262-9C5C-716AAA7518FE
ms.date: 04/10/2019
keywords: ["NDIS_WWAN_UICC_ACCESS_BINARY structure"]
ms.keywords: _NDIS_WWAN_UICC_ACCESS_BINARY, NDIS_WWAN_UICC_ACCESS_BINARY, *PNDIS_WWAN_UICC_ACCESS_BINARY,
req.header: ndiswwan.h
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
req.typenames: NDIS_WWAN_UICC_ACCESS_BINARY, *PNDIS_WWAN_UICC_ACCESS_BINARY
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _NDIS_WWAN_UICC_ACCESS_BINARY
 - ndiswwan/_NDIS_WWAN_UICC_ACCESS_BINARY
 - PNDIS_WWAN_UICC_ACCESS_BINARY
 - ndiswwan/PNDIS_WWAN_UICC_ACCESS_BINARY
 - NDIS_WWAN_UICC_ACCESS_BINARY
 - ndiswwan/NDIS_WWAN_UICC_ACCESS_BINARY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_UICC_ACCESS_BINARY
---

# _NDIS_WWAN_UICC_ACCESS_BINARY structure


## -description

The **NDIS_WWAN_UICC_ACCESS_BINARY** structure describes information about a UICC binary file to read or to which to write.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_UICC_ACCESS_BINARY** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_UICC_ACCESS_BINARY_REVISION_1 |
| Size | sizeof(NDIS_WWAN_UICC_ACCESS_BINARY) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field UiccAccessBinary

A formatted [**WWAN_UICC_ACCESS_BINARY**](../wwan/ns-wwan-_wwan_uicc_access_binary.md) structure that describes the binary UICC file.

## -remarks

This structure is used in the payload of an [OID_WWAN_UICC_ACCESS_BINARY](/windows-hardware/drivers/network/oid-wwan-uicc-access-binary) Query or Set request.

## -see-also

[MB UICC application and file system access](/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_ACCESS_BINARY](/windows-hardware/drivers/network/oid-wwan-uicc-access-binary)

[NDIS_STATUS_WWAN_UICC_BINARY_RESPONSE](/windows-hardware/drivers/network/ndis-status-wwan-uicc-binary-response)

[**WWAN_UICC_ACCESS_BINARY**](../wwan/ns-wwan-_wwan_uicc_access_binary.md)