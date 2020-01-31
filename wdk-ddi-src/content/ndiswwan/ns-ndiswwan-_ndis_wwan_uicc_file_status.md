---
UID: NS:ndiswwan._NDIS_WWAN_UICC_FILE_STATUS
title: _NDIS_WWAN_UICC_FILE_STATUS (ndiswwan.h)
description: The NDIS_WWAN_UICC_FILE_STATUS structure describes the status of a UICC file.
tech.root: netvista
ms.assetid: 7A1325CD-8F65-492E-A943-D3E6BAAD8CDE
ms.date: 04/09/2019
f1_keywords:
 - "ndiswwan/_NDIS_WWAN_UICC_FILE_STATUS"
ms.keywords: _NDIS_WWAN_UICC_FILE_STATUS, NDIS_WWAN_UICC_FILE_STATUS, *PNDIS_WWAN_UICC_FILE_STATUS, 
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
req.typenames: NDIS_WWAN_UICC_FILE_STATUS, *PNDIS_WWAN_UICC_FILE_STATUS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndiswwan.h
api_name: 
- _NDIS_WWAN_UICC_FILE_STATUS
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _NDIS_WWAN_UICC_FILE_STATUS structure

## -description

The **NDIS_WWAN_UICC_FILE_STATUS** structure describes the status of a UICC file. 

## -struct-fields

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_UICC_FILE_STATUS** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_UICC_FILE_STATUS_REVISION_1 |
| Size | sizeof(NDIS_WWAN_UICC_FILE_STATUS) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).
 
### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |
 
### -field UiccFileStatus

A formatted [**WWAN_UICC_FILE_STATUS**](../wwan/ns-wwan-_wwan_uicc_file_status.md) structure that describes the status of the UICC file.

## -remarks

This structure is used in the [NDIS_STATUS_WWAN_UICC_FILE_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-uicc-file-status) status notification in response to a previous [OID_WWAN_UICC_FILE_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-file-status) Query request.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_FILE_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-file-status)

[NDIS_STATUS_WWAN_UICC_FILE_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-uicc-file-status)

[**WWAN_UICC_FILE_STATUS**](../wwan/ns-wwan-_wwan_uicc_file_status.md)
