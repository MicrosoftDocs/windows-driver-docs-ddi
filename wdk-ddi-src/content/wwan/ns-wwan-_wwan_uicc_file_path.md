---
UID: NS:wwan._WWAN_UICC_FILE_PATH
title: _WWAN_UICC_FILE_PATH (wwan.h)
description: The WWAN_UICC_FILE_PATH structure describes file path information about a UICC file. 
tech.root: netvista
ms.assetid: D7D74B4A-EB1D-479A-8206-A904C34B7C43
ms.date: 04/09/2019
ms.topic: struct
f1_keywords:
 - "wwan/_WWAN_UICC_FILE_PATH"
ms.keywords: _WWAN_UICC_FILE_PATH, WWAN_UICC_FILE_PATH, *PWWAN_UICC_FILE_PATH, 
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
req.typenames: WWAN_UICC_FILE_PATH, *PWWAN_UICC_FILE_PATH
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_UICC_FILE_PATH
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_FILE_PATH structure

## -description

The **WWAN_UICC_FILE_PATH** structure describes file path information about a UICC file. 

## -struct-fields

### -field Version

The version number of the structure that follows. In Windows 10, version 1903, this version must be set to **1**.
 
### -field AppIdLength

The size of the application ID, in bytes, as defined in Section 8.3 of the [ETSI TS 102 221 technical specification](https://go.microsoft.com/fwlink/p/?linkid=864594). For 2G cards, this field must be set to zero (0).
 
### -field AppId

The application ID. Only the first **AppIdLength** bytes are meaningful. If the application ID is longer than **WWAN_UICC_APP_ID_MAX_LEN** bytes, then **AppIdLength** specifies the actual length but only the first **WWAN_UICC_APP_ID_MAX_LEN** bytes are in this field.
 
### -field FilePathLength

The size of the file path, in bytes.

### -field FilePath

The file path, which is an array of 16-bit file IDs. The first ID must be either **0x7FFF** or **0x3F00**. If the first ID is **0x7FFF**, then the path is relative to the ADF of the application desginated by **AppId**. Otherwise, it is an absolute path starting from the MF.

## -remarks

This structure is used in the [**NDIS_WWAN_UICC_FILE_PATH**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_file_path.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_FILE_STATUS](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-file-status)

[**NDIS_WWAN_UICC_FILE_PATH**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_file_path.md)
