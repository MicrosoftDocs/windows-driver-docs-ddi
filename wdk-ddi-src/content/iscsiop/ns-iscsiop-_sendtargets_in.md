---
UID: NS:iscsiop._SendTargets_IN
title: _SendTargets_IN (iscsiop.h)
description: The SendTargets_IN structure holds the input data for the SendTargets method.
old-location: storage\sendtargets_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SendTargets_IN structure"]
ms.keywords: "*PSendTargets_IN, PSendTargets_IN, PSendTargets_IN structure pointer [Storage Devices], SendTargets_IN, SendTargets_IN structure [Storage Devices], _SendTargets_IN, iscsiop/PSendTargets_IN, iscsiop/SendTargets_IN, storage.sendtargets_in, structs-iSCSI_448fb50f-6420-43ca-be0e-b3dd110cd48b.xml"
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
req.typenames: SendTargets_IN, *PSendTargets_IN
f1_keywords:
 - _SendTargets_IN
 - iscsiop/_SendTargets_IN
 - PSendTargets_IN
 - iscsiop/PSendTargets_IN
 - SendTargets_IN
 - iscsiop/SendTargets_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - _SendTargets_IN
 - PSendTargets_IN
 - SendTargets_IN
---

# _SendTargets_IN structure


## -description

The SendTargets_IN structure holds the input data for the <a href="/windows-hardware/drivers/storage/sendtargets">SendTargets</a> method.

## -struct-fields

### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The LoginToTarget and AddConnectionToSession methods both return this value in their UniqueSessionId parameter.

### -field SendTargetsText

The authentication key text in the PDU.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>



<a href="/windows-hardware/drivers/storage/sendtargets">SendTargets</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_sendtargets_out">SendTargets_OUT</a>

