---
UID: NS:winsplp._SPLCLIENT_INFO_INTERNAL
tech.root: print
title: SPLCLIENT_INFO_INTERNAL (winsplp.h)
ms.date: 01/18/2024
targetos: Windows
description: The SPLCLIENT_INFO_INTERNAL structure is a super set of the information in splclient_info_1, splclient_info2 and splclient_info3 and contains additional information needed by the Device Control Defender code.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: winsplp.h
req.include-header: Winsplp.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: 
req.target-type: 
req.typenames: SPLCLIENT_INFO_INTERNAL
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - _SPLCLIENT_INFO_INTERNAL
 - SPLCLIENT_INFO_INTERNAL
f1_keywords:
 - _SPLCLIENT_INFO_INTERNAL
 - winsplp/_SPLCLIENT_INFO_INTERNAL
 - SPLCLIENT_INFO_INTERNAL
 - winsplp/SPLCLIENT_INFO_INTERNAL
dev_langs:
 - c++
helpviewer_keywords:
 - _SPLCLIENT_INFO_INTERNAL
---

## -description

The **SPLCLIENT_INFO_INTERNAL** structure is a super set of the information in splclient_info_1, splclient_info2 and splclient_info3 and contains additional information needed by the Device Control Defender code.

## -struct-fields

### -field cbSize

Size in bytes of this structure.

### -field dwFlags

Open printer additional flags to the provider.

### -field dwSize

Reserved for compatibility with a info 1 structure.

### -field pMachineName

Client machine name

### -field pUserName

Client user name

### -field dwBuildNum

Client build number

### -field dwMajorVersion

Client machine major version

### -field dwMinorVersion

Client machine minor version

### -field wProcessorArchitecture

Client machine architecture

### -field hSplPrinter

Server side handle to be used for direct calls.

### -field dwProcessId

ProcessId of the app that is calling OpenPrinter.

### -field dwSessionId

SessionId of the app session that is calling OpenPrinter.

## -remarks

## -see-also
