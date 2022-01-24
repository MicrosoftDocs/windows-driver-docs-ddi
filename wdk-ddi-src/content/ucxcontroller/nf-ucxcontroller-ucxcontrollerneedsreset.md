---
UID: NF:ucxcontroller.UcxControllerNeedsReset
title: UcxControllerNeedsReset function (ucxcontroller.h)
description: Initiates a non-Plug and Play (PnP) controller reset operation by queuing an event into the controller reset state machine.
old-location: buses\_ucxcontrollerneedsreset.htm
tech.root: usbref
ms.date: 01/14/2022
keywords: ["UcxControllerNeedsReset function"]
ms.keywords: UcxControllerNeedsReset, UcxControllerNeedsReset method [Buses], buses._ucxcontrollerneedsreset, ucxcontroller/UcxControllerNeedsReset
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UcxControllerNeedsReset
 - ucxcontroller/UcxControllerNeedsReset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Ucxcontroller.h
api_name:
 - UcxControllerNeedsReset
---

# UcxControllerNeedsReset function

## -description

Initiates a non-Plug and Play (PnP) controller reset operation by queuing an event into the controller reset state machine.

## -parameters

### -param Controller [in]

A handle to the controller object to reset. The client driver retrieved the handle in a previous call to [UcxControllerCreate](nf-ucxcontroller-ucxcontrollercreate.md).

## -remarks

If the operation is successful, the method returns TRUE. Otherwise, it returns FALSE.

## -see-also

- [UcxControllerCreate](nf-ucxcontroller-ucxcontrollercreate.md)
