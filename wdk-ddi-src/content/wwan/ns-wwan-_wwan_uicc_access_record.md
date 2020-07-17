---
UID: NS:wwan._WWAN_UICC_ACCESS_RECORD
title: _WWAN_UICC_ACCESS_RECORD (wwan.h)
description: The WWAN_UICC_ACCESS_RECORD structure describes information about a UICC linear fixed or cyclic file to read or to which to write. 
tech.root: netvista
ms.assetid: 04C39F78-66B1-4AC6-A66D-49DB0829DCF1
ms.date: 04/10/2019
keywords: ["_WWAN_UICC_ACCESS_RECORD structure"]
f1_keywords:
 - "wwan/_WWAN_UICC_ACCESS_RECORD"
 - "_WWAN_UICC_ACCESS_RECORD"
ms.keywords: _WWAN_UICC_ACCESS_RECORD, WWAN_UICC_ACCESS_RECORD, *PWWAN_UICC_ACCESS_RECORD, 
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
req.typenames: WWAN_UICC_ACCESS_RECORD, *PWWAN_UICC_ACCESS_RECORD
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name:  
- _WWAN_UICC_ACCESS_RECORD
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_ACCESS_RECORD structure

## -description

The **WWAN_UICC_ACCESS_RECORD** structure describes information about a UICC linear fixed or cyclic file to read or to which to write. 

## -struct-fields

### -field Version

The version number of the structure that follows. In Windows 10, version 1903, this version must be set to **1**.
 
### -field AppId

The application ID.

### -field UiccFilePath

A formatted [**WWAN_UICC_FILE_PATH**](../wwan/ns-wwan-_wwan_uicc_file_path.md) structure that describes the file path of the UICC linear fixed or cyclic file.

### -field RecordNumber

The record number. This represents the absolute record index at all times. Relative record access is not supported because the modem can perform multiple accesses on a file (NEXT, PREVIOUS).

### -field LocalPinSize

The size of the password, in bytes.

### -field LocalPin

The password for the UICC.

### -field RecordDataSize

The size of the record data, in bytes.

### -field RecordData

Used only in Set (write) operations. Contains the data to write to the file.

## -remarks

This structure is used in the [**NDIS_WWAN_UICC_ACCESS_RECORD**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_access_record.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_ACCESS_RECORD](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-access-record)

[**NDIS_WWAN_UICC_ACCESS_RECORD**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_access_record.md)
