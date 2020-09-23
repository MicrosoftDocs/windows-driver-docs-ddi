---
UID: NF:fcb.RxpDereferenceAndFinalizeNetFcb
title: RxpDereferenceAndFinalizeNetFcb function (fcb.h)
description: RxpDereferenceAndFinalizeNetFcb decrements the reference count and finalizes an FCB structure.
old-location: ifsk\rxpdereferenceandfinalizenetfcb.htm
tech.root: ifsk
ms.assetid: 954a4811-4515-4ed4-a4f1-df598d08fc77
ms.date: 04/16/2018
keywords: ["RxpDereferenceAndFinalizeNetFcb function"]
ms.keywords: RxpDereferenceAndFinalizeNetFcb, RxpDereferenceAndFinalizeNetFcb function [Installable File System Drivers], fcb/RxpDereferenceAndFinalizeNetFcb, ifsk.rxpdereferenceandfinalizenetfcb, rxref_474f30d3-858e-4179-8236-3068a2325818.xml
req.header: fcb.h
req.include-header: Fcb.h
req.target-type: Desktop
req.target-min-winverclnt: The RxpDereferenceAndFinalizeNetFcb routine is only available on Windows Server 2003 Service Pack 1 (SP1) and later.
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
 - RxpDereferenceAndFinalizeNetFcb
 - fcb/RxpDereferenceAndFinalizeNetFcb
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fcb.h
api_name:
 - RxpDereferenceAndFinalizeNetFcb
---

# RxpDereferenceAndFinalizeNetFcb function


## -description

<b>RxpDereferenceAndFinalizeNetFcb</b> decrements the reference count and finalizes an FCB structure.

## -parameters

### -param ThisFcb

<p>A pointer to the FCB structure to be dereferenced and finalized.</p>

### -param RxContext 

[in]
A pointer to the RX_CONTEXT structure associated with the <i>Fcb</i> parameter.

### -param RecursiveFinalize 

[in]
A parameter that indicates if this should be a recursive finalize operation.

### -param ForceFinalize 

[in]
A parameter that indicates if this routine should force the <i>Fcb</i> parameter to be finalized.

## -returns

<b>RxpDereferenceAndFinalizeNetFcb</b> returns <b>TRUE</b> if the FCB was finalized.

## -remarks

The referencing and dereferencing of FCBs is different from those of the other data structures because of the embedded resource in the FCB. This implies that the caller requires information regarding the status of the FCB (whether it was finalized or not ).To finalize the FCB, two locks need to be held, the NET_ROOT name table lock as well as the FCB resource. <b>RxpDereferenceAndFinalizeNetFcb</b> acquires the additional lock if required to finalize the FCB.

On checked builds, <b>RxpDereferenceAndFinalizeNetFcb</b> causes the system to ASSERT if <i>ForceFinalize</i> is <b>FALSE</b>, if the node type for the structure is not an FCB, or if the FCB was acquired exclusive.

## -see-also

<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpreferencenetfcb">RxpReferenceNetFcb</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxptrackdereference">RxpTrackDereference</a>



<a href="/windows-hardware/drivers/ddi/fcb/nf-fcb-rxptrackreference">RxpTrackReference</a>