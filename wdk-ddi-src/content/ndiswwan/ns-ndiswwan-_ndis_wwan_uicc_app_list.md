---
UID: NS:ndiswwan._NDIS_WWAN_UICC_APP_LIST
title: _NDIS_WWAN_UICC_APP_LIST (ndiswwan.h)
description: The NDIS_WWAN_UICC_APP_LIST structure describes a list of applications in a UICC and information about them.
tech.root: netvista
ms.assetid: 7ACDB2C7-0971-4FFA-8E8D-7CE291B68CA7
ms.date: 04/08/2019
keywords: ["NDIS_WWAN_UICC_APP_LIST structure"]
ms.keywords: _NDIS_WWAN_UICC_APP_LIST, NDIS_WWAN_UICC_APP_LIST, *PNDIS_WWAN_UICC_APP_LIST,
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
req.typenames: NDIS_WWAN_UICC_APP_LIST, *PNDIS_WWAN_UICC_APP_LIST
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _NDIS_WWAN_UICC_APP_LIST
 - ndiswwan/_NDIS_WWAN_UICC_APP_LIST
 - PNDIS_WWAN_UICC_APP_LIST
 - ndiswwan/PNDIS_WWAN_UICC_APP_LIST
 - NDIS_WWAN_UICC_APP_LIST
 - ndiswwan/NDIS_WWAN_UICC_APP_LIST
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - _NDIS_WWAN_UICC_APP_LIST
---

# _NDIS_WWAN_UICC_APP_LIST structure


## -description

The **NDIS_WWAN_UICC_APP_LIST** structure describes a list of applications in a UICC and information about them.

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_UICC_APP_LIST** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_UICC_APP_LIST_REVISION_1 |
| Size | sizeof(NDIS_WWAN_UICC_APP_LIST) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).

### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |

### -field UiccAppList

A formatted [**WWAN_UICC_APP_LIST**](../wwan/ns-wwan-_wwan_uicc_app_list.md) structure that describes the list of applications in the UICC, and information about them.

## -remarks

This structure is used in the [NDIS_STATUS_WWAN_UICC_APP_LIST](/windows-hardware/drivers/network/ndis-status-wwan-uicc-app-list) status notification in response to a previous [OID_WWAN_UICC_APP_LIST](/windows-hardware/drivers/network/oid-wwan-uicc-app-list) Query request.

## -see-also

[MB UICC application and file system access](/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_APP_LIST](/windows-hardware/drivers/network/oid-wwan-uicc-app-list)

[NDIS_STATUS_WWAN_UICC_APP_LIST](/windows-hardware/drivers/network/ndis-status-wwan-uicc-app-list)

[**WWAN_UICC_APP_LIST**](../wwan/ns-wwan-_wwan_uicc_app_list.md)