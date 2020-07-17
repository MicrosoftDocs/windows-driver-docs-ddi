---
UID: NE:ntifs._SRV_INSTANCE_TYPE
title: _SRV_INSTANCE_TYPE (ntifs.h)
description: The SRV_INSTANCE_TYPE enumeration type describes the SRV instance type for an SRV_OPEN_ECP_CONTEXT.
tech.root: ifsk
ms.assetid: c7ae9f16-5a28-478a-8099-a5a9524a36d8
ms.date: 09/09/2019
keywords: ["_SRV_INSTANCE_TYPE enumeration"]
ms.keywords: "SRV_INSTANCE_TYPE, SRV_INSTANCE_TYPE enumeration [Installable File System Drivers], *PSRV_INSTANCE_TYPE"
f1_keywords:
 - "ntifs/SRV_INSTANCE_TYPE"
 - "SRV_INSTANCE_TYPE"
dev_langs:
 - c++
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- SRV_INSTANCE_TYPE
product:
- Windows
targetos: Windows
req.typenames: SRV_INSTANCE_TYPE
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
