---
UID: NF:rxprocs.RxReference
title: RxReference function (rxprocs.h)
description: RxReference increments the NodeReferenceCount member of a structure by one for several of the reference counted data structures used by RDBSS.
old-location: ifsk\rxreference.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RxReference function"]
ms.keywords: RxReference, RxReference function [Installable File System Drivers], ifsk.rxreference, rxprocs/RxReference, rxref_3c87a6aa-d0c8-4308-8152-fce322dcb035.xml
req.header: rxprocs.h
req.include-header: Rxprocs.h
req.target-type: Desktop
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RxReference
 - rxprocs/RxReference
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxprocs.h
api_name:
 - RxReference
---

# RxReference function


## -description

<b>RxReference</b> increments the <b>NodeReferenceCount</b> member of a structure by one for several of the reference counted data structures used by RDBSS.

## -parameters

### -param Instance [in, out]


A pointer to the reference-counted data structure to be referenced (incremented).

## -remarks

The <b>RxReference</b> routine can be used to reference (increment by one) the <b>NodeReferenceCount</b> member on the following data structures used by RDBSS:

SRV_CALL

NET_ROOT

V_NET_ROOT

SRV_OPEN

FOBX

If <b>RxReference</b> is called with any other type of RDBSS data structure, the routine causes the system to ASSERT on checked builds.

## -see-also

<a href="/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>
