---
UID: NS:ndis._NDIS_RW_LOCK_REFCOUNT
title: "_NDIS_RW_LOCK_REFCOUNT"
author: windows-driver-content
description: The NDIS_RW_LOCK_REFCOUNT union defines attributes of a read/write lock.
old-location: netvista\ndis_rw_lock_refcount.htm
old-project: netvista
ms.assetid: 1b2c93dd-a80e-4197-bc4f-cad12f6d6c77
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_RW_LOCK_REFCOUNT, _NDIS_RW_LOCK_REFCOUNT, NDIS_RW_LOCK_REFCOUNT union [Network Drivers Starting with Windows Vista], ndis_processor_group_ref_55aa679b-460e-43a3-8ad2-678926bbf200.xml, ndis/NDIS_RW_LOCK_REFCOUNT, netvista.ndis_rw_lock_refcount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Obsolete in NDIS 6.20 and later. Supported for NDIS 6.0 and NDIS 5.1 in   Windows Vista and Windows 7. Supported for NDIS 5.1 drivers in Windows XP.
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_RW_LOCK_REFCOUNT
product: Windows
targetos: Windows
req.typenames: NDIS_RW_LOCK_REFCOUNT
---

# _NDIS_RW_LOCK_REFCOUNT structure


## -description


The <b>NDIS_RW_LOCK_REFCOUNT</b> union defines attributes of a read/write lock. This union is opaque to NDIS
   drivers.
   


## -syntax


````
typedef union _NDIS_RW_LOCK_REFCOUNT {
  ;      // Reserved for NDIS.
} NDIS_RW_LOCK_REFCOUNT;
````


## -struct-fields

