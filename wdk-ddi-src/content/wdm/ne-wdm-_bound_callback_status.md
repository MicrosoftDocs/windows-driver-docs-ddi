---
UID: NE:wdm._BOUND_CALLBACK_STATUS
title: "_BOUND_CALLBACK_STATUS"
author: windows-driver-content
description: The BOUND_CALLBACK_STATUS enumeration indicates how a user-mode bounds exception was processed by the BoundCallback function.
old-location: kernel\bound_callback_status.htm
old-project: kernel
ms.assetid: 874FB2E1-7A2F-4C91-BA72-D67DA2EE84E1
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PBOUND_CALLBACK_STATUS, BOUND_CALLBACK_STATUS, BOUND_CALLBACK_STATUS enumeration [Kernel-Mode Driver Architecture], BoundExceptionContinueSearch, BoundExceptionError, BoundExceptionHandled, BoundExceptionMaximum, _BOUND_CALLBACK_STATUS, kernel.bound_callback_status, wdm/BOUND_CALLBACK_STATUS, wdm/BoundExceptionContinueSearch, wdm/BoundExceptionError, wdm/BoundExceptionHandled, wdm/BoundExceptionMaximum"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	BOUND_CALLBACK_STATUS
product:
- Windows
targetos: Windows
req.typenames: BOUND_CALLBACK_STATUS, *PBOUND_CALLBACK_STATUS
req.product: Windows 10 or later.
---

# _BOUND_CALLBACK_STATUS enumeration


## -description


The <b>BOUND_CALLBACK_STATUS</b> enumeration indicates how a user-mode bounds exception was processed by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn957853">BoundCallback</a> function.


## -enum-fields




### -field BoundExceptionContinueSearch

The bounds exception was not handled by the callback, and the exception should continue to propagate.  


### -field BoundExceptionHandled

The exception was handled by the callback, and the exception should not propagate any further. 


### -field BoundExceptionError

The user mode process should be terminated by the system.


### -field BoundExceptionMaximum

This value is not currently used.


## -remarks



The return value of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn957853">BoundCallback</a> routine is a <b>BOUND_CALLBACK_STATUS</b> value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn957853">BoundCallback</a>
 

 

