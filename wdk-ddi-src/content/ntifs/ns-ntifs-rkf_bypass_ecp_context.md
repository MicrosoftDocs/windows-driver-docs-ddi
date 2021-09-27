---
UID: NS:ntifs._RKF_BYPASS_ECP_CONTEXT
tech.root: ifsk
title: RKF_BYPASS_ECP_CONTEXT
ms.date: 09/09/2021
targetos: Windows
description: Learn more about the RKF_BYPASS_ECP_CONTEXT structure.
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
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: RKF_BYPASS_ECP_CONTEXT, *PRKF_BYPASS_ECP_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _RKF_BYPASS_ECP_CONTEXT
 - PRKF_BYPASS_ECP_CONTEXT
 - RKF_BYPASS_ECP_CONTEXT
f1_keywords:
 - _RKF_BYPASS_ECP_CONTEXT
 - ntifs/_RKF_BYPASS_ECP_CONTEXT
 - PRKF_BYPASS_ECP_CONTEXT
 - ntifs/PRKF_BYPASS_ECP_CONTEXT
 - RKF_BYPASS_ECP_CONTEXT
 - ntifs/RKF_BYPASS_ECP_CONTEXT
dev_langs:
 - c++
---

## -description

The **RKF_BYPASS_ECP_CONTEXT** structure contains the extra create parameter (ECP) context for the Resume Key Filter (RKF)  for an RKF bypass handle.

## -struct-fields

### -field Reserved

Reserved for future use. Must be set to zero.

### -field Version

The version of the ECP context (this structure). Must be initialized to zero.

## -remarks

The value GUID_ECP_RKF_BYPASS is used when calling support routines such as [**FltAllocateExtraCreateParameter**](../fltkernel/nf-fltkernel-fltallocateextracreateparameter.md) and [**FsRtlRemoveExtraCreateParameter**](nf-ntifs-fsrtlremoveextracreateparameter.md).

See [Introduction to extra create parameters](/windows-hardware/drivers/ifs/introduction-to-extra-create-parameters) for more information.
