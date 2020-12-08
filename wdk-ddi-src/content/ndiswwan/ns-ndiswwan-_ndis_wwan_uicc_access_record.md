---
UID: NS:ndiswwan._NDIS_WWAN_UICC_ACCESS_RECORD
title: _NDIS_WWAN_UICC_ACCESS_RECORD (ndiswwan.h)
description: The NDIS_WWAN_UICC_ACCESS_RECORD structure describes information about a UICC linear fixed or cyclic file to read or to which to write.
tech.root: netvista
ms.date: 04/10/2019
keywords: ["NDIS_WWAN_UICC_ACCESS_RECORD structure"]
ms.keywords: _NDIS_WWAN_UICC_ACCESS_RECORD, NDIS_WWAN_UICC_ACCESS_RECORD, *PNDIS_WWAN_UICC_ACCESS_RECORD,
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
req.typenames: NDIS_WWAN_UICC_ACCESS_RECORD, *PNDIS_WWAN_UICC_ACCESS_RECORD
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _NDIS_WWAN_UICC_ACCESS_RECORD
 - ndiswwan/_NDIS_WWAN_UICC_ACCESS_RECORD
 - PNDIS_WWAN_UICC_ACCESS_RECORD
 - ndiswwan/PNDIS_WWAN_UICC_ACCESS_RECORD
 - NDIS_WWAN_UICC_ACCESS_RECORD
 - ndiswwan/NDIS_WWAN_UICC_ACCESS_RECORD
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_UICC_ACCESS_RECORD
---

# _NDIS_WWAN_UICC_ACCESS_RECORD structure


## -description

The **NDIS_WWAN_UICC_ACCESS_RECORD** structure describes information about a UICC linear fixed or cyclic file to read or to which to write.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_UICC_ACCESS_RECORD** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_UICC_ACCESS_RECORD_REVISION_1 |
| Size | sizeof(NDIS_WWAN_UICC_ACCESS_RECORD) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field UiccAccessRecord

A formatted [**WWAN_UICC_ACCESS_RECORD**](../wwan/ns-wwan-_wwan_uicc_access_record.md) structure that describes the linear fixed or cyclic UICC file.

## -remarks

This structure is used in the payload of an [OID_WWAN_UICC_ACCESS_RECORD](/windows-hardware/drivers/network/oid-wwan-uicc-access-record) Query or Set request.

## -see-also

[MB UICC application and file system access](/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_ACCESS_RECORD](/windows-hardware/drivers/network/oid-wwan-uicc-access-record)

[NDIS_STATUS_WWAN_UICC_RECORD_RESPONSE](/windows-hardware/drivers/network/ndis-status-wwan-uicc-record-response)

[**WWAN_UICC_ACCESS_RECORD**](../wwan/ns-wwan-_wwan_uicc_access_record.md)
