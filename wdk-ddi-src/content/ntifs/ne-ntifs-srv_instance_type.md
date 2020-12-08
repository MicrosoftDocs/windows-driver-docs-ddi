---
UID: NE:ntifs._SRV_INSTANCE_TYPE
title: _SRV_INSTANCE_TYPE (ntifs.h)
description: The SRV_INSTANCE_TYPE enumeration type describes the SRV instance type for an SRV_OPEN_ECP_CONTEXT.
tech.root: ifsk
ms.date: 09/09/2019
keywords: ["SRV_INSTANCE_TYPE enumeration"]
ms.keywords: "SRV_INSTANCE_TYPE, SRV_INSTANCE_TYPE enumeration [Installable File System Drivers], *PSRV_INSTANCE_TYPE"
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.typenames: SRV_INSTANCE_TYPE
f1_keywords:
 - _SRV_INSTANCE_TYPE
 - ntifs/_SRV_INSTANCE_TYPE
 - PSRV_INSTANCE_TYPE
 - ntifs/PSRV_INSTANCE_TYPE
 - SRV_INSTANCE_TYPE
 - ntifs/SRV_INSTANCE_TYPE
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - SRV_INSTANCE_TYPE
---

# _SRV_INSTANCE_TYPE enumeration


## -description

The SRV_INSTANCE_TYPE enumeration type describes the SRV instance type for an [SRV_OPEN_ECP_CONTEXT](ns-ntifs-_srv_open_ecp_context.md).

## -enum-fields

### -field SrvInstanceTypeUndefined

The SRV instance type is undefined.

### -field SrvInstanceTypePrimary

The open request came from a primary instance of SRV with user-facing shares.

### -field SrvInstanceTypeCsv

The open request came from an internal instance of SRV used by CSVFS.

### -field SrvInstanceTypeSBL

The open request came from an internal instance of SRV used by S2D at Software Layer Bus (SBL).

### -field SrvInstanceTypeSR

The open request came from an internal instance of SRV used by Storage Replica.

## -see-also

[SRV_OPEN_ECP_CONTEXT](ns-ntifs-_srv_open_ecp_context.md)

