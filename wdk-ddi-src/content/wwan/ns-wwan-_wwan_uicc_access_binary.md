---
UID: NS:wwan._WWAN_UICC_ACCESS_BINARY
title: _WWAN_UICC_ACCESS_BINARY (wwan.h)
description: The WWAN_UICC_ACCESS_BINARY structure describes information about a UICC binary file to read or to which to write. 
tech.root: netvista
ms.assetid: D22866FC-A344-4D8B-B4C4-A72DF90F1505
ms.date: 04/10/2019
ms.topic: struct
ms.keywords: _WWAN_UICC_ACCESS_BINARY, WWAN_UICC_ACCESS_BINARY, *PWWAN_UICC_ACCESS_BINARY, 
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
req.typenames: WWAN_UICC_ACCESS_BINARY, *PWWAN_UICC_ACCESS_BINARY
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_UICC_ACCESS_BINARY
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_ACCESS_BINARY structure

## -description

The **WWAN_UICC_ACCESS_BINARY** structure describes information about a UICC binary file to read or to which to write. 

## -struct-fields

### -field Version

The version number of the structure that follows. In Windows 10, version 1903, this version must be set to **1**.
 
### -field AppId

The application ID.

### -field UiccFilePath

A formatted [**WWAN_UICC_FILE_PATH**](../wwan/ns-wwan-_wwan_uicc_file_path.md) structure that describes the file path of the UICC binary file.

### -field FileOffset

The offset to use when reading from the file. This field can be bigger than 256, and it combines both offset high and offset low as defined in the [ETSI TS 102 221 technical specification](https://go.microsoft.com/fwlink/p/?linkid=864594).

### -field NumberOfBytes

The number of bytes to be read. For example, a client driver could use this function to read a transparent (binary) file that is larger than 256 bytes, although the maximum amount that can be read or written in a single UICC operation is 256 bytes per the [ETSI TS 102 221 technical specification](https://go.microsoft.com/fwlink/p/?linkid=864594). It is the function's responsibility to split this into multiple APDUs and send the result back in a single response.

### -field LocalPinSize

The size of the password, in bytes.

### -field LocalPin

The password for the UICC.

### -field BinaryDataSize

The size of the binary data, in bytes.

### -field BinaryData

Used only in Set (write) operations. Contains the data to write to the file.

## -remarks

This structure is used in the [**NDIS_WWAN_UICC_ACCESS_BINARY**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_access_binary.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_ACCESS_BINARY](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-access-binary)

[**NDIS_WWAN_UICC_ACCESS_BINARY**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_access_binary.md)