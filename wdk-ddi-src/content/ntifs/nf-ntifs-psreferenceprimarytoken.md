---
UID: NF:ntifs.PsReferencePrimaryToken
title: PsReferencePrimaryToken function (ntifs.h)
description: Learn more about the PsReferencePrimaryToken function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["PsReferencePrimaryToken function"]
ms.keywords: PsReferencePrimaryToken, PsReferencePrimaryToken routine [Installable File System Drivers], ifsk.psreferenceprimarytoken, ntifs/PsReferencePrimaryToken, psref_021aea60-1707-4817-9169-95a3dc79adb6.xml
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PsReferencePrimaryToken
 - ntifs/PsReferencePrimaryToken
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsReferencePrimaryToken
---

# PsReferencePrimaryToken function

## -description

The **PsReferencePrimaryToken** routine increments the reference count of the primary token for the specified process.

## -parameters

### -param Process [in, out]

Pointer to the process whose primary token's reference count is to be incremented.

## -returns

**PsReferencePrimaryToken** returns a pointer to the primary token for the given process.

## -remarks

**PsReferencePrimaryToken** increments the reference count of the returned primary token. Thus for every successful call to **PsReferencePrimaryToken**, the primary token's reference count must be decremented by calling one of the following functions:

* **ObDereferenceObject**, for Windows 2000
* **PsDereferencePrimaryToken**, for Microsoft Windows XP and later

For more information about security and access control, see [Windows security model for driver developers](/windows-hardware/drivers/driversecurity/windows-security-model) and the documentation on these topics in the Windows SDK.

## -see-also

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)

[**PsDereferencePrimaryToken**](nf-ntifs-psdereferenceprimarytoken.md)

[**PsReferenceImpersonationToken**](nf-ntifs-psreferenceimpersonationtoken.md)

[**SeQueryInformationToken**](nf-ntifs-sequeryinformationtoken.md)
