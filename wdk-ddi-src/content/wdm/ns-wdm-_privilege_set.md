---
UID: NS:wdm._PRIVILEGE_SET
title: PRIVILEGE_SET (wdm.h)
description: The PRIVILEGE_SET structure specifies a set of security privileges.
old-location: kernel\privilege_set.htm
tech.root: kernel
ms.date: 07/15/2022
keywords: ["PRIVILEGE_SET structure"]
ms.keywords: "*PPRIVILEGE_SET, PPRIVILEGE_SET, PPRIVILEGE_SET structure pointer [Kernel-Mode Driver Architecture], PRIVILEGE_SET, PRIVILEGE_SET structure [Kernel-Mode Driver Architecture], _PRIVILEGE_SET, kernel.privilege_set, kstruct_c_c599935e-9092-4ee4-a982-a105835eb6bd.xml, wdm/PNP_BUS_INFORMATION, wdm/PPRIVILEGE_SET"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: PRIVILEGE_SET, *PPRIVILEGE_SET
f1_keywords:
 - _PRIVILEGE_SET
 - wdm/_PRIVILEGE_SET
 - PPRIVILEGE_SET
 - wdm/PPRIVILEGE_SET
 - PRIVILEGE_SET
 - wdm/PRIVILEGE_SET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _PRIVILEGE_SET
 - PPRIVILEGE_SET
 - PRIVILEGE_SET
---

# PRIVILEGE_SET structure

## -description

The **PRIVILEGE_SET** structure specifies a set of security privileges. It is also used to indicate which, if any, privileges are held by a user or group requesting access to an object.

## -struct-fields

### -field PrivilegeCount

The number of privileges in the privilege set.

### -field Control

Specifies a control flag related to the privileges. The PRIVILEGE_SET_ALL_NECESSARY control flag is currently defined. It indicates that all of the specified privileges must be held by the process requesting access. If this flag is not set, the presence of any privileges in the user's access token grants the access.

### -field Privilege

Specifies an array of [**LUID_AND_ATTRIBUTES**](ns-wdm-_luid_and_attributes.md) structures describing the set's privileges. The following attributes are defined for privileges.

| Value | Meaning |
| ----- | ------- |
| SE_PRIVILEGE_ENABLED_BY_DEFAULT | The privilege is enabled by default. |
| SE_PRIVILEGE_ENABLED            | The privilege is enabled. |
| SE_PRIVILEGE_USED_FOR_ACCESS    | The privilege was used to gain access to an object or service. This flag is used to identify the relevant privileges in a set passed by a client application that may contain unnecessary privileges. |

## -remarks

A privilege is used to control access to an object or service more strictly than is typical with discretionary access control. A system manager uses privileges to control which users are able to manipulate system resources. An application uses privileges when it changes a system-wide resource, such as when it changes the system time or shuts down the system.

## -see-also

[**SeAccessCheck**](nf-wdm-seaccesscheck.md)

[**PRIVILEGE_SET** structure (winnt.h)](/windows/win32/api/winnt/ns-winnt-privilege_set)
