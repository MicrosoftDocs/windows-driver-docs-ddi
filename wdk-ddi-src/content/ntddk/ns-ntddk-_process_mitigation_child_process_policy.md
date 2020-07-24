---
UID: NS:ntddk._PROCESS_MITIGATION_CHILD_PROCESS_POLICY
title: _PROCESS_MITIGATION_CHILD_PROCESS_POLICY (ntddk.h)
description: Stores policy information about creating child processes.
old-location: kernel\process_mitigation_child_process_policy.htm
tech.root: kernel
ms.assetid: 8f388c0e-41ee-40e4-b633-687eeff74a0a
ms.date: 04/30/2018
keywords: ["_PROCESS_MITIGATION_CHILD_PROCESS_POLICY structure"]
ms.keywords: "*PPROCESS_MITIGATION_CHILD_PROCESS_POLICY, PROCESS_MITIGATION_CHILD_PROCESS_POLICY, PROCESS_MITIGATION_CHILD_PROCESS_POLICY structure [Kernel-Mode Driver Architecture], _PROCESS_MITIGATION_CHILD_PROCESS_POLICY, kernel.process_mitigation_child_process_policy, ntddk/PROCESS_MITIGATION_CHILD_PROCESS_POLICY"
f1_keywords:
 - "ntddk/PROCESS_MITIGATION_CHILD_PROCESS_POLICY"
 - "PROCESS_MITIGATION_CHILD_PROCESS_POLICY"
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
- Ntddk.h
api_name:
- PROCESS_MITIGATION_CHILD_PROCESS_POLICY
targetos: Windows
req.typenames: PROCESS_MITIGATION_CHILD_PROCESS_POLICY, *PPROCESS_MITIGATION_CHILD_PROCESS_POLICY
---

# _PROCESS_MITIGATION_CHILD_PROCESS_POLICY structure


## -description


Stores policy information about creating child processes.


## -struct-fields




### -field DUMMYUNIONNAME


### -field DUMMYUNIONNAME.Flags

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.NoChildProcessCreation

If set, the process cannot create child processes.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.AuditNoChildProcessCreation

If set, causes audit events to be generated when child processes are created by the process. If both <b>NoChildProcessCreation</b> and <b>AuditNoChildProcessCreation</b> are set, <b>NoChildProcessCreation</b> takes precedence over audit setting.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.AllowSecureProcessCreation

Denies creation of child processes unless the child process is a secure process and if creation was previously blocked. It allows a process to spawn a child process on behalf of another process that cannot itself create child processes. See PROCESS_CREATION_CHILD_PROCESS_OVERRIDE in <a href="https://docs.microsoft.com/windows/desktop/api/processthreadsapi/nf-processthreadsapi-updateprocthreadattribute">UpdateProcThreadAttribute</a>.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.ReservedFlags

Reserved.

