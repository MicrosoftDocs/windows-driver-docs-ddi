---
UID: NS:ntifs.BULK_SECURITY_TEST_DATA
tech.root: ifsk
title: BULK_SECURITY_TEST_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the BULK_SECURITY_TEST_DATA structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: BULK_SECURITY_TEST_DATA, *PBULK_SECURITY_TEST_DATA
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - BULK_SECURITY_TEST_DATA
 - PBULK_SECURITY_TEST_DATA
f1_keywords:
 - BULK_SECURITY_TEST_DATA
 - ntifs/BULK_SECURITY_TEST_DATA
 - PBULK_SECURITY_TEST_DATA
 - ntifs/PBULK_SECURITY_TEST_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - BULK_SECURITY_TEST_DATA
---

## -description

The **BULK_SECURITY_TEST_DATA** structure is used with the [**FSCTL_SECURITY_ID_CHECK**](ni-ntifs-fsctl_security_id_check.md) control code to verify security identifiers (SIDs) against specified access rights in bulk.

## -struct-fields

### -field DesiredAccess

An [**ACCESS_MASK**](/windows/win32/secauthz/access-mask) value that specifies the access rights to be checked against the provided security identifiers. This mask defines the permissions required for the operation.

### -field SecurityIds[1]

An array of security identifiers (SIDs) to be tested.

## -see-also

[**FSCTL_SECURITY_ID_CHECK**](ni-ntifs-fsctl_security_id_check.md)

[**ACCESS_MASK**](/windows/win32/secauthz/access-mask)
