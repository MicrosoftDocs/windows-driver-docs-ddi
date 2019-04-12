---
UID: NS:ndiswwan._NDIS_WWAN_UICC_RESPONSE
title: _NDIS_WWAN_UICC_RESPONSE (ndiswwan.h)
description: The NDIS_WWAN_UICC_RESPONSE structure describes a UICC response to a file read or write operation.
tech.root: netvista
ms.assetid: 765B74B7-0609-4A2F-BCF7-A5BBF9C15D32
ms.date: 04/10/2019
ms.topic: struct
ms.keywords: _NDIS_WWAN_UICC_RESPONSE, NDIS_WWAN_UICC_RESPONSE, *PNDIS_WWAN_UICC_RESPONSE, 
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
req.typenames: NDIS_WWAN_UICC_RESPONSE, *PNDIS_WWAN_UICC_RESPONSE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndiswwan.h
api_name: 
- _NDIS_WWAN_UICC_RESPONSE
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _NDIS_WWAN_UICC_RESPONSE structure

## -description

The **NDIS_WWAN_UICC_RESPONSE** structure describes a UICC response to a file read or write operation. 

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_UICC_RESPONSE** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_UICC_RESPONSE_REVISION_1 |
| Size | sizeof(NDIS_WWAN_UICC_RESPONSE) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).
 
### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |
 
### -field UiccResponse

A formatted [**WWAN_UICC_RESPONSE**](../wwan/ns-wwan-_wwan_uicc_response.md) structure that describes the UICC's response.

## -remarks

This structure is used in either the [NDIS_STATUS_WWAN_UICC_BINARY_RESPONSE](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-uicc-binary-response) status notification in response to a previous [OID_WWAN_UICC_ACCESS_BINARY](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-access-binary) Query or Set request, or in an [NDIS_STATUS_WWAN_UICC_RECORD_RESPONSE](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-uicc-record-response) status notification in response to a previous [OID_WWAN_UICC_ACCESS_RECORD](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-access-record) Query or Set request.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_ACCESS_BINARY](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-access-binary)

[NDIS_STATUS_WWAN_UICC_BINARY_RESPONSE](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-uicc-app-list)

[OID_WWAN_UICC_ACCESS_RECORD](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-access-record)

[NDIS_STATUS_WWAN_UICC_RECORD_RESPONSE](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-uicc-record-response)

[**WWAN_UICC_RESPONSE**](../wwan/ns-wwan-_wwan_uicc_response.md)