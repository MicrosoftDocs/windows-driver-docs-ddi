---
UID: NS:ntifs._NETWORK_APP_INSTANCE_EA
title: _NETWORK_APP_INSTANCE_EA (ntifs.h)
description: An Extended Attribute (EA) structure for processes using Server Message Block (SMB) Cluster Client Failover.
ms.date: 10/19/2018
tech.root: ifsk
keywords: ["NETWORK_APP_INSTANCE_EA structure"]
ms.keywords: _NETWORK_APP_INSTANCE_EA, NETWORK_APP_INSTANCE_EA, *PNETWORK_APP_INSTANCE_EA,
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: CCFFilter.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NETWORK_APP_INSTANCE_EA, *PNETWORK_APP_INSTANCE_EA
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NETWORK_APP_INSTANCE_EA
 - ntifs/_NETWORK_APP_INSTANCE_EA
 - PNETWORK_APP_INSTANCE_EA
 - ntifs/PNETWORK_APP_INSTANCE_EA
 - NETWORK_APP_INSTANCE_EA
 - ntifs/NETWORK_APP_INSTANCE_EA
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _NETWORK_APP_INSTANCE_EA
 - PNETWORK_APP_INSTANCE_EA
 - NETWORK_APP_INSTANCE_EA
dev_langs:
 - c++
---

# _NETWORK_APP_INSTANCE_EA structure


## -description

An Extended Attribute (EA) structure for processes using Server Message Block (SMB) Cluster Client Failover.

## -struct-fields

### -field AppInstanceID

A GUID that identifies a single application instance, or a **NETWORK_APP_INSTANCE_EA** structure when the application additionally contains a flag for **CsvFlags**.

### -field CsvFlags

An optional flag:
`NETWORK_APP_INSTANCE_CSV_FLAGS_VALID_ONLY_IF_CSV_COORDINATOR (0x00000001)`

The **NETWORK_APP_INSTANCE_CSV_FLAGS_VALID_ONLY_IF_CSV_COORDINATOR** flag is only used when the file is opened directly from CSVFS. This flag is ignored when the file is opened using the SMB protocol. The flag notifies CSVFS that the file only be opened on the coordinating node. If an ‘open’ request is sent to CSVFS and the node is non-coordinating, then the open will fail. Additionally, if the coordinating node is moved while the file is opened, the file open would be invalidated.

## -remarks

A process can register a CCF application ID using [**RegisterAppInstance**](/windows/win32/api/smbclnt/nf-smbclnt-registerappinstance), enabling all 'open' operations from the process to have the same ApplicationId. If an ID isn't registered, the ApplicationId will differ for each operation.

To mark individual open operations with a different ApplicationId, first set **AppInstanceID** to a GUID value. you can then append **SMB_CCF_APP_INSTANCE_EA_NAME** to the list of Extended Attributes when calling [NtCreateFile](./nf-ntifs-ntcreatefile.md). If the application also passes the  **NETWORK_APP_INSTANCE_CSV_FLAGS_VALID_ONLY_IF_CSV_COORDINATOR** flag, then **AppInstanceID** should be **NETWORK_APP_INSTANCE_EA** structure.

