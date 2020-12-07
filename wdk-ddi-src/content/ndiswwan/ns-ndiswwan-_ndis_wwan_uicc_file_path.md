---
UID: NS:ndiswwan._NDIS_WWAN_UICC_FILE_PATH
title: _NDIS_WWAN_UICC_FILE_PATH (ndiswwan.h)
description: The NDIS_WWAN_UICC_FILE_PATH structure describes file path information about a UICC file.
tech.root: netvista
ms.date: 04/09/2019
keywords: ["NDIS_WWAN_UICC_FILE_PATH structure"]
ms.keywords: _NDIS_WWAN_UICC_FILE_PATH, NDIS_WWAN_UICC_FILE_PATH, *PNDIS_WWAN_UICC_FILE_PATH,
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
req.typenames: NDIS_WWAN_UICC_FILE_PATH, *PNDIS_WWAN_UICC_FILE_PATH
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _NDIS_WWAN_UICC_FILE_PATH
 - ndiswwan/_NDIS_WWAN_UICC_FILE_PATH
 - PNDIS_WWAN_UICC_FILE_PATH
 - ndiswwan/PNDIS_WWAN_UICC_FILE_PATH
 - NDIS_WWAN_UICC_FILE_PATH
 - ndiswwan/NDIS_WWAN_UICC_FILE_PATH
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_UICC_FILE_PATH
---

# _NDIS_WWAN_UICC_FILE_PATH structure


## -description

The **NDIS_WWAN_UICC_FILE_PATH** structure describes file path information about a UICC file.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_UICC_FILE_PATH** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_UICC_FILE_PATH_REVISION_1 |
| Size | sizeof(NDIS_WWAN_UICC_FILE_PATH) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field UiccFilePath

A formatted [**WWAN_UICC_FILE_PATH**](../wwan/ns-wwan-_wwan_uicc_file_path.md) structure that describes the file path for the UICC file.

## -remarks

This structure is used in the payload of an [OID_WWAN_UICC_FILE_STATUS](/windows-hardware/drivers/network/oid-wwan-uicc-file-status) Query request.

## -see-also

[MB UICC application and file system access](/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_FILE_STATUS](/windows-hardware/drivers/network/oid-wwan-uicc-file-status)

[NDIS_STATUS_WWAN_UICC_FILE_STATUS](/windows-hardware/drivers/network/ndis-status-wwan-uicc-file-status)

[**WWAN_UICC_FILE_PATH**](../wwan/ns-wwan-_wwan_uicc_file_path.md)
