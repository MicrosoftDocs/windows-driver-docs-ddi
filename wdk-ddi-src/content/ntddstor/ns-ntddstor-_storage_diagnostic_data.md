---
UID: NS:ntddstor._STORAGE_DIAGNOSTIC_DATA
title: _STORAGE_DIAGNOSTIC_DATA (ntddstor.h)
description: Describes diagnostic data about the storage driver stack. The STORAGE_DIAGNOSTIC_DATA structure is provided in the output buffer of an IOCTL_STORAGE_DIAGNOSTIC request.
old-location: storage\storage_diagnostic_data.htm
tech.root: storage
ms.assetid: 68BC990B-DD0C-49CD-95EC-672FD1459B39
ms.date: 03/29/2018
keywords: ["_STORAGE_DIAGNOSTIC_DATA structure"]
ms.keywords: "*PSTORAGE_DIAGNOSTIC_DATA, PSTORAGE_DIAGNOSTIC_DATA, PSTORAGE_DIAGNOSTIC_DATA structure pointer [Storage Devices], STORAGE_DIAGNOSTIC_DATA, STORAGE_DIAGNOSTIC_DATA structure [Storage Devices], _STORAGE_DIAGNOSTIC_DATA, ntddstor/PSTORAGE_DIAGNOSTIC_DATA, ntddstor/STORAGE_DIAGNOSTIC_DATA, storage.storage_diagnostic_data"
f1_keywords:
 - "ntddstor/STORAGE_DIAGNOSTIC_DATA"
 - "STORAGE_DIAGNOSTIC_DATA"
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddstor.h
api_name:
- STORAGE_DIAGNOSTIC_DATA
product:
- Windows
targetos: Windows
req.typenames: STORAGE_DIAGNOSTIC_DATA, *PSTORAGE_DIAGNOSTIC_DATA
---

# _STORAGE_DIAGNOSTIC_DATA structure


## -description


Describes  diagnostic data about the storage driver stack. The <b>STORAGE_DIAGNOSTIC_DATA</b> structure is provided in the output buffer of an  <a href="https://msdn.microsoft.com/5F71CCBE-F93F-4DCD-A673-1D6DE49C7400">IOCTL_STORAGE_DIAGNOSTIC</a> request.


## -struct-fields




### -field Version

Version of this structure.


### -field Size

Specifies the whole size of the structure and the associated data buffer.


### -field ProviderId

Specifies the GUID of a diagnostic data provider.


### -field BufferSize

If the request failed because of buffer too small, this field should be filled with the required buffer
    size for a <i>DiagnosticDataBuffer</i> needed by provider;
     if the request is successful, it should be filled with returned buffer size of <i>DiagnosticDataBuffer</i>;
     it should be cleared to zero for other cases.


### -field Reserved

Reserved for future use.


### -field DiagnosticDataBuffer

Specifies the Diagnostic data buffer.


## -see-also




<a href="https://msdn.microsoft.com/5F71CCBE-F93F-4DCD-A673-1D6DE49C7400">IOCTL_STORAGE_DIAGNOSTIC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_diagnostic_request">STORAGE_DIAGNOSTIC_REQUEST</a>
 

 

